---
title: "writeonly_texture_view クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::graphics::writeonly_texture_view
dev_langs:
- C++
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
caps.latest.revision: 9
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
ms.openlocfilehash: a40aa0cb433b6daee19af7fdea7c6421b61c1b4c
ms.lasthandoff: 02/24/2017

---
# <a name="writeonlytextureview-class"></a>writeonly_texture_view クラス
テクスチャへの書き込み専用アクセスを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view;  
 
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value_type`  
 テクスチャの要素の型。  
  
 `_Rank`  
 テクスチャのランク。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`scalar_type`||  
|`value_type`|テクスチャの要素の型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[writeonly_texture_view コンス トラクター](#ctor)|`writeonly_texture_view` クラスの新しいインスタンスを初期化します。|  
|[~ writeonly_texture_view デストラクター](#ctor)|`writeonly_texture_view` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[set メソッド](#set)|指定されたインデックス位置にある要素の値を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator = 演算子](#operator_eq)|指定したコピー`writeonly_texture_view`オブジェクトをこのオブジェクトにします。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[rank 定数](#rank)|`writeonly_texture_view` オブジェクトのランクを取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_Texture_base`  
  
 `writeonly_texture_view`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_graphics.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="a-namedtora-writeonlytextureview"></a><a name="dtor"></a>~ writeonly_texture_view 

 `writeonly_texture_view` オブジェクトを破棄します。  
  
```  
~writeonly_texture_view() restrict(amp,cpu);
```  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

 指定したコピー`writeonly_texture_view`オブジェクトをこのオブジェクトにします。  
  
```  
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `writeonly_texture_view`コピーするオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `writeonly_texture_view` オブジェクトへの参照。  
  
##  <a name="a-nameranka-rank"></a><a name="rank"></a>ランク 

 `writeonly_texture_view` オブジェクトのランクを取得します。  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>設定 

 指定されたインデックス位置にある要素の値を設定します。  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 要素のインデックス。  
  
 `value`  
 要素の新しい値。  
  
##  <a name="a-namectora-writeonlytextureview"></a><a name="ctor"></a>writeonly_texture_view 

 `writeonly_texture_view` クラスの新しいインスタンスを初期化します。  
  
```  
writeonly_texture_view(
    texture<value_type, 
    _Rank>& _Src) restrict(amp);

 
writeonly_texture_view(
    const writeonly_texture_view<value_type,  
    _Rank>& _Src) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rank`  
 テクスチャのランク。  
  
 `value_type`  
 テクスチャの要素の型。  
  
 `_Src`  
 作成に使用されるテクスチャ、`writeonly_texture_view`です。  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)

