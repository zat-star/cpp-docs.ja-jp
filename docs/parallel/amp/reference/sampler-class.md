---
title: "sampler クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 090e05e294646b7571a3d06ca8ed23583a306756
ms.lasthandoff: 02/24/2017

---
# <a name="sampler-class"></a>sampler クラス
サンプラーのクラスは、テクスチャ サンプリングに使用するサンプリング構成情報を集計します。  
  
## <a name="syntax"></a>構文  
  
```  
class sampler;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[サンプラー コンス トラクター](#ctor)|オーバーロードされます。 サンプラーのインスタンスを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get_address_mode メソッド](#get_address_mode)|サンプラー オブジェクトに関連付けられている `address_mode` を返します。|  
|[get_border_color メソッド](#get_border_color)|サンプラー オブジェクトに関連付けられている境界線の色を返します。|  
|[get_filter_mode メソッド](#get_filter_mode)|サンプラー オブジェクトに関連付けられている `filter_mode` を返します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator = 演算子](#operator_eq)|オーバーロードされます。 代入演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[address_mode データ メンバー](#address_mode)|`sampler` オブジェクトのアドレス モードを取得します。|  
|[border_color データ メンバー](#border_color)|`sampler` オブジェクトの境界線の色を取得します。|  
|[filter_mode データ メンバー](#filter_mode)|`sampler` オブジェクトのフィルター モードを取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `sampler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_graphics.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="a-namectora-sampler"></a><a name="ctor"></a>サンプラー 

 インスタンスを構築、 [sampler クラス](sampler-class.md)します。  
  
```  
sampler() restrict(cpu);

 *// [1] default constructor  
 
sampler(// [2] constructor  
    filter_mode _Filter_mode) restrict(cpu);

 
sampler(// [3] constructor  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [4] constructor  
    filter_mode _Filter_mode,  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [5] copy constructor  
    const sampler& _Other) restrict(amp,
    cpu);

 
sampler(// [6] move constructor  
    sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filter_mode`  
 サンプリングで使用するフィルター モード。  
  
 `_Address_mode`  
 すべての次元のサンプリングで使用されるアドレッシング モード。  
  
 `_Border_color`  
 アドレス モードが address_border である場合に使用される境界線の色。 既定値は `float_4(0.0f, 0.0f, 0.0f, 0.0f)` です。  
  
 `_Other`  
 [5] コピー コンストラクター  
 新しい `sampler` インスタンスにコピーする `sampler` オブジェクト。  
  
 [6] 移動コンス トラクター  
 新しい `sampler` インスタンスに移動する `sampler` オブジェクト。  
  
##  <a name="a-nameaddressmodea-addressmode"></a><a name="address_mode"></a>address_mode 

 `sampler` オブジェクトのアドレス モードを取得します。  
  
```  
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;  
```  
  
##  <a name="a-namebordercolora-bordercolor"></a><a name="border_color"></a>border_color 

 `sampler` オブジェクトの境界線の色を取得します。  
  
```  
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;  
```  
  
##  <a name="a-namefiltermodea-filtermode"></a><a name="filter_mode"></a>filter_mode 

 `sampler` オブジェクトのフィルター モードを取得します。  
  
```  
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;  
```  
  
##  <a name="a-namegetaddressmodea-getaddressmode"></a><a name="get_address_mode"></a>get_address_mode 

 この `sampler` のために構成されたフィルター モードを返します。  
  
```  
Concurrency::graphics::address_mode get_address_mode() const __GPU;  
```  
  
### <a name="return-value"></a>戻り値  
 サンプラーのために構成されたアドレス モード。  
  
##  <a name="a-namegetbordercolora-getbordercolor"></a><a name="get_border_color"></a>get_border_color 

 この `sampler` に構成された境界線の色を返します。  
  
```  
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>戻り値  
 境界線の色が含まれる float_4。  
  
##  <a name="a-namegetfiltermodea-getfiltermode"></a><a name="get_filter_mode"></a>get_filter_mode 

 この `sampler` のために構成されたフィルター モードを返します。  
  
```  
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>戻り値  
 サンプラーのために構成されたフィルター モード。  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

 別のサンプラー オブジェクトの値を既存のサンプラーに割り当てます。  
  
```  
sampler& operator= (// [1] copy assignment operator const sampler& _Other) restrict(amp,
    cpu);

 
sampler& operator= (// [2] move assingment operator sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 [1] 代入演算子をコピーします  
 この `sampler` にコピーする `sampler` オブジェクト。  
  
 [2] 代入演算子を移動します  
 この `sampler` に移動する `sampler` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 このサンプラーのインスタンスへの参照。  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)

