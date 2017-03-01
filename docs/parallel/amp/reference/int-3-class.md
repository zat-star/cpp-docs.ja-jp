---
title: "int_3 クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::int_3::get_x
- amp_short_vectors/Concurrency::graphics::int_3::operator-=
- amp_short_vectors/Concurrency::graphics::int_3::get_y
- amp_short_vectors/Concurrency::graphics::int_3::operator=
- amp_short_vectors/Concurrency::graphics::int_3::operator++
- amp_short_vectors/Concurrency::graphics::int_3::zyx
- amp_short_vectors/Concurrency::graphics::int_3::get_z
- amp_short_vectors/Concurrency::graphics::int_3::operator*=
- amp_short_vectors/Concurrency::graphics::int_3::grb
- amp_short_vectors/Concurrency::graphics::int_3::get_xz
- amp_short_vectors/Concurrency::graphics::int_3::br
- amp_short_vectors/Concurrency::graphics::int_3::operator--
- amp_short_vectors/Concurrency::graphics::int_3
- amp_short_vectors/Concurrency::graphics::int_3::set_yx
- amp_short_vectors/Concurrency::graphics::int_3::x
- amp_short_vectors/Concurrency::graphics::int_3::yxz
- amp_short_vectors/Concurrency::graphics::int_3::set_y
- amp_short_vectors/Concurrency::graphics::int_3::zy
- amp_short_vectors/Concurrency::graphics::int_3::z
- amp_short_vectors/Concurrency::graphics::int_3::get_zx
- amp_short_vectors/Concurrency::graphics::int_3::rb
- amp_short_vectors/Concurrency::graphics::int_3::yzx
- amp_short_vectors/Concurrency::graphics::int_3::gb
- amp_short_vectors/Concurrency::graphics::int_3::set_zxy
- amp_short_vectors/Concurrency::graphics::int_3::xy
- amp_short_vectors/Concurrency::graphics::int_3::set_zx
- amp_short_vectors/Concurrency::graphics::int_3::g
- amp_short_vectors/Concurrency::graphics::int_3::operator/=
- amp_short_vectors/Concurrency::graphics::int_3::get_zy
- amp_short_vectors/Concurrency::graphics::int_3::yx
- amp_short_vectors/Concurrency::graphics::int_3::xzy
- amp_short_vectors/Concurrency::graphics::int_3::set_x
- amp_short_vectors/Concurrency::graphics::int_3::set_xz
- amp_short_vectors/Concurrency::graphics::int_3::get_yzx
- amp_short_vectors/Concurrency::graphics::int_3::b
- amp_short_vectors/Concurrency::graphics::int_3::gbr
- amp_short_vectors/Concurrency::graphics::int_3::operator+=
- amp_short_vectors/Concurrency::graphics::int_3::gr
- amp_short_vectors/Concurrency::graphics::int_3::brg
- amp_short_vectors/Concurrency::graphics::int_3::bg
- amp_short_vectors/Concurrency::graphics::int_3::zx
- amp_short_vectors/Concurrency::graphics::int_3::get_xyz
- amp_short_vectors/Concurrency::graphics::int_3::set_zyx
- amp_short_vectors/Concurrency::graphics::int_3::set_yzx
- amp_short_vectors/Concurrency::graphics::int_3::y
- amp_short_vectors/Concurrency::graphics::int_3::set_z
- amp_short_vectors/Concurrency::graphics::int_3::r
- amp_short_vectors/Concurrency::graphics::int_3::set_xzy
- amp_short_vectors/Concurrency::graphics::int_3::rg
- amp_short_vectors/Concurrency::graphics::int_3::xyz
- amp_short_vectors/Concurrency::graphics::int_3::get_yz
- amp_short_vectors/Concurrency::graphics::int_3::operator-
- amp_short_vectors/Concurrency::graphics::int_3::set_xy
- amp_short_vectors/Concurrency::graphics::int_3::zxy
- amp_short_vectors/Concurrency::graphics::int_3::yz
- amp_short_vectors/Concurrency::graphics::int_3::set_zy
- amp_short_vectors/Concurrency::graphics::int_3::bgr
- amp_short_vectors/Concurrency::graphics::int_3::get_xzy
- amp_short_vectors/Concurrency::graphics::int_3::get_yx
- amp_short_vectors/Concurrency::graphics::int_3::rbg
- amp_short_vectors/Concurrency::graphics::int_3::get_zxy
- amp_short_vectors/Concurrency::graphics::int_3::set_yxz
- amp_short_vectors/Concurrency::graphics::int_3::rgb
- amp_short_vectors/Concurrency::graphics::int_3::get_xy
- amp_short_vectors/Concurrency::graphics::int_3::set_xyz
- amp_short_vectors/Concurrency::graphics::int_3::get_yxz
- amp_short_vectors/Concurrency::graphics::int_3::get_zyx
- amp_short_vectors/Concurrency::graphics::int_3::xz
- amp_short_vectors/Concurrency::graphics::int_3::set_yz
dev_langs:
- C++
ms.assetid: d4af182f-30f1-455c-b16d-aa99cd314038
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
ms.openlocfilehash: 038b3cafdbdc628fdff0bcf70db6575acabb17e1
ms.lasthandoff: 02/24/2017

---
# <a name="int3-class"></a>int_3 クラス
3 個の整数の short ベクターを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class int_3;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[int_3 コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター。すべての要素を 0 で初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|int_3::get_x メソッド||  
|int_3::get_xy メソッド||  
|int_3::get_xyz メソッド||  
|int_3::get_xz メソッド||  
|int_3::get_xzy メソッド||  
|int_3::get_y メソッド||  
|int_3::get_yx メソッド||  
|int_3::get_yxz メソッド||  
|int_3::get_yz メソッド||  
|int_3::get_yzx メソッド||  
|int_3::get_z メソッド||  
|int_3::get_zx メソッド||  
|int_3::get_zxy メソッド||  
|int_3::get_zy メソッド||  
|int_3::get_zyx メソッド||  
|int_3::ref_b メソッド||  
|int_3::ref_g メソッド||  
|int_3::ref_r メソッド||  
|int_3::ref_x メソッド||  
|int_3::ref_y メソッド||  
|int_3::ref_z メソッド||  
|int_3::set_x メソッド||  
|int_3::set_xy メソッド||  
|int_3::set_xyz メソッド||  
|int_3::set_xz メソッド||  
|int_3::set_xzy メソッド||  
|int_3::set_y メソッド||  
|int_3::set_yx メソッド||  
|int_3::set_yxz メソッド||  
|int_3::set_yz メソッド||  
|int_3::set_yzx メソッド||  
|int_3::set_z メソッド||  
|int_3::set_zx メソッド||  
|int_3::set_zxy メソッド||  
|int_3::set_zy メソッド||  
|int_3::set_zyx メソッド||  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|int_3::operator- 演算子||  
|int_3::operator-- 演算子||  
|int_3::operator%= 演算子||  
|int_3::operator&= 演算子||  
|int_3::operator*= 演算子||  
|int_3::operator/= 演算子||  
|int_3::operator^= 演算子||  
|int_3::operator | = 演算子||  
|int_3::operator~ 演算子||  
|int_3::operator++ 演算子||  
|int_3::operator+= 演算子||  
|int_3::operator\<= 演算子||  
|int_3::operator= 演算子||  
|int_3::operator-= 演算子||  
|int_3::operator >> = 演算子||  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[定数のサイズ](#size)||  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|int_3::b データ メンバー||  
|int_3::bg データ メンバー||  
|int_3::bgr データ メンバー||  
|int_3::br データ メンバー||  
|int_3::brg データ メンバー||  
|int_3::g データ メンバー||  
|int_3::gb データ メンバー||  
|int_3::gbr データ メンバー||  
|int_3::gr データ メンバー||  
|int_3::grb データ メンバー||  
|int_3::r データ メンバー||  
|int_3::rb データ メンバー||  
|int_3::rbg データ メンバー||  
|int_3::rg データ メンバー||  
|int_3::rgb データ メンバー||  
|int_3::x データ メンバー||  
|int_3::xy データ メンバー||  
|int_3::xyz データ メンバー||  
|int_3::xz データ メンバー||  
|int_3::xzy データ メンバー||  
|int_3::y データ メンバー||  
|int_3::yx データ メンバー||  
|int_3::yxz データ メンバー||  
|int_3::yz データ メンバー||  
|int_3::yzx データ メンバー||  
|int_3::z データ メンバー||  
|int_3::zx データ メンバー||  
|int_3::zxy データ メンバー||  
|int_3::zy データ メンバー||  
|int_3::zyx データ メンバー||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `int_3`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_short_vectors.h  
  
 **Namespace:** concurrency::graphics  

## <a name="a-namectora-int3"></a><a name="ctor"></a>int_3 

既定のコンストラクター。すべての要素を 0 で初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
int_3() restrict(amp,cpu);  
int_3(  
   int _V0,  
   int _V1,  
   int _V2  
) restrict(amp,cpu);  
int_3(  
   int _V  
) restrict(amp,cpu);  
int_3(  
   const int_3& _Other  
) restrict(amp,cpu);  
explicit inline int_3(  
   const uint_3& _Other  
) restrict(amp,cpu);  
explicit inline int_3(  
   const float_3& _Other  
) restrict(amp,cpu);  
explicit inline int_3(  
   const unorm_3& _Other  
) restrict(amp,cpu);  
explicit inline int_3(  
   const norm_3& _Other  
) restrict(amp,cpu);  
explicit inline int_3(  
   const double_3& _Other  
) restrict(amp,cpu);  
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
  
## <a name="a-namesizea-size"></a><a name="size"></a>サイズ 

## <a name="syntax"></a>構文  
  
```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)

