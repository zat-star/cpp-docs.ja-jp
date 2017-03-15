---
title: "uint_3 クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::uint_3::get_xz
- amp_short_vectors/Concurrency::graphics::uint_3::set_yzx
- amp_short_vectors/Concurrency::graphics::uint_3::get_y
- amp_short_vectors/Concurrency::graphics::uint_3::get_yzx
- amp_short_vectors/Concurrency::graphics::uint_3::get_yz
- amp_short_vectors/Concurrency::graphics::uint_3::yzx
- amp_short_vectors/Concurrency::graphics::uint_3::get_z
- amp_short_vectors/Concurrency::graphics::uint_3::z
- amp_short_vectors/Concurrency::graphics::uint_3::xy
- amp_short_vectors/Concurrency::graphics::uint_3::gr
- amp_short_vectors/Concurrency::graphics::uint_3::operator=
- amp_short_vectors/Concurrency::graphics::uint_3::x
- amp_short_vectors/Concurrency::graphics::uint_3::gbr
- amp_short_vectors/Concurrency::graphics::uint_3::set_xy
- amp_short_vectors/Concurrency::graphics::uint_3::g
- amp_short_vectors/Concurrency::graphics::uint_3::set_yz
- amp_short_vectors/Concurrency::graphics::uint_3::br
- amp_short_vectors/Concurrency::graphics::uint_3::get_xyz
- amp_short_vectors/Concurrency::graphics::uint_3::b
- amp_short_vectors/Concurrency::graphics::uint_3::get_yxz
- amp_short_vectors/Concurrency::graphics::uint_3::set_zyx
- amp_short_vectors/Concurrency::graphics::uint_3::get_x
- amp_short_vectors/Concurrency::graphics::uint_3::rgb
- amp_short_vectors/Concurrency::graphics::uint_3::set_zy
- amp_short_vectors/Concurrency::graphics::uint_3::brg
- amp_short_vectors/Concurrency::graphics::uint_3::set_xyz
- amp_short_vectors/Concurrency::graphics::uint_3::xyz
- amp_short_vectors/Concurrency::graphics::uint_3::set_zxy
- amp_short_vectors/Concurrency::graphics::uint_3
- amp_short_vectors/Concurrency::graphics::uint_3::get_xy
- amp_short_vectors/Concurrency::graphics::uint_3::set_yx
- amp_short_vectors/Concurrency::graphics::uint_3::get_zyx
- amp_short_vectors/Concurrency::graphics::uint_3::get_zxy
- amp_short_vectors/Concurrency::graphics::uint_3::set_y
- amp_short_vectors/Concurrency::graphics::uint_3::yx
- amp_short_vectors/Concurrency::graphics::uint_3::grb
- amp_short_vectors/Concurrency::graphics::uint_3::operator+=
- amp_short_vectors/Concurrency::graphics::uint_3::set_x
- amp_short_vectors/Concurrency::graphics::uint_3::operator/=
- amp_short_vectors/Concurrency::graphics::uint_3::rbg
- amp_short_vectors/Concurrency::graphics::uint_3::set_zx
- amp_short_vectors/Concurrency::graphics::uint_3::set_z
- amp_short_vectors/Concurrency::graphics::uint_3::get_zx
- amp_short_vectors/Concurrency::graphics::uint_3::bgr
- amp_short_vectors/Concurrency::graphics::uint_3::get_xzy
- amp_short_vectors/Concurrency::graphics::uint_3::get_yx
- amp_short_vectors/Concurrency::graphics::uint_3::bg
- amp_short_vectors/Concurrency::graphics::uint_3::r
- amp_short_vectors/Concurrency::graphics::uint_3::xzy
- amp_short_vectors/Concurrency::graphics::uint_3::zyx
- amp_short_vectors/Concurrency::graphics::uint_3::set_xz
- amp_short_vectors/Concurrency::graphics::uint_3::rg
- amp_short_vectors/Concurrency::graphics::uint_3::zxy
- amp_short_vectors/Concurrency::graphics::uint_3::zy
- amp_short_vectors/Concurrency::graphics::uint_3::yz
- amp_short_vectors/Concurrency::graphics::uint_3::zx
- amp_short_vectors/Concurrency::graphics::uint_3::gb
- amp_short_vectors/Concurrency::graphics::uint_3::operator--
- amp_short_vectors/Concurrency::graphics::uint_3::set_yxz
- amp_short_vectors/Concurrency::graphics::uint_3::get_zy
- amp_short_vectors/Concurrency::graphics::uint_3::operator++
- amp_short_vectors/Concurrency::graphics::uint_3::operator-
- amp_short_vectors/Concurrency::graphics::uint_3::y
- amp_short_vectors/Concurrency::graphics::uint_3::xz
- amp_short_vectors/Concurrency::graphics::uint_3::rb
- amp_short_vectors/Concurrency::graphics::uint_3::operator*=
- amp_short_vectors/Concurrency::graphics::uint_3::yxz
- amp_short_vectors/Concurrency::graphics::uint_3::set_xzy
- amp_short_vectors/Concurrency::graphics::uint_3::operator-=
dev_langs:
- C++
ms.assetid: 5e22c277-9d4f-4a3a-b38c-a83d5fcab33c
caps.latest.revision: 10
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
ms.openlocfilehash: 4bb1f7e1a971050dfc1616deb178c8fe834bc351
ms.lasthandoff: 02/24/2017

---
# <a name="uint3-class"></a>uint_3 クラス
3 個の符号なし整数の short ベクターを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class uint_3;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[uint_3 コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター。すべての要素を 0 で初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|uint_3::get_x メソッド||  
|uint_3::get_xy メソッド||  
|uint_3::get_xyz メソッド||  
|uint_3::get_xz メソッド||  
|uint_3::get_xzy メソッド||  
|uint_3::get_y メソッド||  
|uint_3::get_yx メソッド||  
|uint_3::get_yxz メソッド||  
|uint_3::get_yz メソッド||  
|uint_3::get_yzx メソッド||  
|uint_3::get_z メソッド||  
|uint_3::get_zx メソッド||  
|uint_3::get_zxy メソッド||  
|uint_3::get_zy メソッド||  
|uint_3::get_zyx メソッド||  
|uint_t::ref_b メソッド||  
|uint_t::ref_g メソッド||  
|uint_t::ref_r メソッド||  
|uint_t::ref_x メソッド||  
|uint_t::ref_y メソッド||  
|uint_t::ref_z メソッド||  
|uint_3::set_x メソッド||  
|uint_3::set_xy メソッド||  
|uint_3::set_xyz メソッド||  
|uint_3::set_xz メソッド||  
|uint_3::set_xzy メソッド||  
|uint_3::set_y メソッド||  
|uint_3::set_yx メソッド||  
|uint_3::set_yxz メソッド||  
|uint_3::set_yz メソッド||  
|uint_3::set_yzx メソッド||  
|uint_3::set_z メソッド||  
|uint_3::set_zx メソッド||  
|uint_3::set_zxy メソッド||  
|uint_3::set_zy メソッド||  
|uint_3::set_zyx メソッド||  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|uint_3::operator-- 演算子||  
|uint_3::operator%= 演算子||  
|uint_3::operator&= 演算子||  
|uint_3::operator*= 演算子||  
|uint_3::operator/= 演算子||  
|uint_3::operator^= 演算子||  
|uint_3::operator | = 演算子||  
|uint_3::operator~ 演算子||  
|uint_3::operator++ 演算子||  
|uint_3::operator+= 演算子||  
|uint_3::operator\<= 演算子||  
|uint_3::operator= 演算子||  
|uint_3::operator-= 演算子||  
|uint_3::operator >> = 演算子||  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[定数のサイズ](#uint_3__size)||  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|uint_3::b データ メンバー||  
|uint_3::bg データ メンバー||  
|uint_3::bgr データ メンバー||  
|uint_3::br データ メンバー||  
|uint_3::brg データ メンバー||  
|uint_3::g データ メンバー||  
|uint_3::gb データ メンバー||  
|uint_3::gbr データ メンバー||  
|uint_3::gr データ メンバー||  
|uint_3::grb データ メンバー||  
|uint_3::r データ メンバー||  
|uint_3::rb データ メンバー||  
|uint_3::rbg データ メンバー||  
|uint_3::rg データ メンバー||  
|uint_3::rgb データ メンバー||  
|uint_3::x データ メンバー||  
|uint_3::xy データ メンバー||  
|uint_3::xyz データ メンバー||  
|uint_3::xz データ メンバー||  
|uint_3::xzy データ メンバー||  
|uint_3::y データ メンバー||  
|uint_3::yx データ メンバー||  
|uint_3::yxz データ メンバー||  
|uint_3::yz データ メンバー||  
|uint_3::yzx データ メンバー||  
|uint_3::z データ メンバー||  
|uint_3::zx データ メンバー||  
|uint_3::zxy データ メンバー||  
|uint_3::zy データ メンバー||  
|uint_3::zyx データ メンバー||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `uint_3`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_short_vectors.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="a-namectora-uint3"></a><a name="ctor"></a>uint_3 

 既定のコンストラクター。すべての要素を 0 で初期化します。  
  
```  
uint_3() restrict(amp,
    cpu);

 
uint_3(
    unsigned int _V0,  
    unsigned int _V1,  
    unsigned int _V2) restrict(amp,
    cpu);

 
uint_3(
    unsigned int _V) restrict(amp,
    cpu);

 
uint_3(
    const uint_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const int_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const float_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const unorm_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const norm_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const double_3& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_V0`  
 0 の要素を初期化する値。  
  
 `_V1`  
 1 の要素を初期化する値。  
  
 `_V2`  
 2 の要素を初期化する値。  
  
 `_V`  
 初期化の値です。  
  
 `_Other`  
 初期化するために使用するオブジェクト。  
  
##  <a name="a-nameuint3sizea-size"></a><a name="uint_3__size"></a>サイズ 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)

