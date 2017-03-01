---
title: "unorm_2 クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator+=
- amp_short_vectors/Concurrency::graphics::unnorm_2::y
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::x
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator--
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator*=
- amp_short_vectors/Concurrency::graphics::unnorm_2::xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator=
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::rg
- amp_short_vectors/Concurrency::graphics::unorm_2
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-=
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator/=
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::gr
- amp_short_vectors/Concurrency::graphics::unnorm_2::r
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::g
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator++
dev_langs:
- C++
ms.assetid: 62e88ea7-e29f-4f62-95ce-61a1f39f5e34
caps.latest.revision: 11
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
ms.openlocfilehash: 8c4e7cd3040e9d9d6d3c3a5a915118fbc815aebf
ms.lasthandoff: 02/24/2017

---
# <a name="unorm2-class"></a>unorm_2 クラス
2 個の符号なし正規数の short ベクターを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class unorm_2;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[unorm_2 コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター。すべての要素を 0 で初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|unorm_2::get_x メソッド||  
|unorm_2::get_xy メソッド||  
|unorm_2::get_y メソッド||  
|unorm_2::get_yx メソッド||  
|unorm_2::ref_g メソッド||  
|unorm_2::ref_r メソッド||  
|unorm_2::ref_x メソッド||  
|unorm_2::ref_y メソッド||  
|unorm_2::set_x メソッド||  
|unorm_2::set_xy メソッド||  
|unorm_2::set_y メソッド||  
|unorm_2::set_yx メソッド||  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|unorm_2::operator-- 演算子||  
|unorm_2::operator*= 演算子||  
|unorm_2::operator/= 演算子||  
|unorm_2::operator++ 演算子||  
|unorm_2::operator+= 演算子||  
|unorm_2::operator= 演算子||  
|unorm_2::operator-= 演算子||  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|unorm_2::size 定数||  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|unorm_2::g データ メンバー||  
|unorm_2::gr データ メンバー||  
|unorm_2::r データ メンバー||  
|unorm_2::rg データ メンバー||  
|unorm_2::x データ メンバー||  
|unorm_2::xy データ メンバー||  
|unorm_2::y データ メンバー||  
|unorm_2::yx データ メンバー||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `unorm_2`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_short_vectors.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="a-namectora-unorm2"></a><a name="ctor"></a>unorm_2 

 既定のコンストラクター。すべての要素を 0 で初期化します。  
  
```  
unorm_2() restrict(amp,
    cpu);

 
unorm_2(
    unorm _V0,  
    unorm _V1) restrict(amp,
    cpu);

 
unorm_2(
    float _V0,  
    float _V1) restrict(amp,
    cpu);

 
unorm_2(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_2(
    float _V) restrict(amp,
    cpu);

 
unorm_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const double_2& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_V0`  
 0 の要素を初期化する値。  
  
 `_V1`  
 1 の要素を初期化する値。  
  
 `_V`  
 初期化の値です。  
  
 `_Other`  
 初期化するために使用するオブジェクト。  
  
##  <a name="a-nameunorm2sizea-size"></a><a name="unorm_2__size"></a>サイズ 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)

