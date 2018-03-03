---
title: "CSimpleMapEqualHelper クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ecc32dc8e6e9b249b0b8b334ec3d08bf26cbd1ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper クラス
このクラスは、のヘルパー、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelper
```  
  
#### <a name="parameters"></a>パラメーター  
 `TKey`  
 主な要素です。  
  
 `TVal`  
 値の要素。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(静的)2 つのキーの等価性をテストします。|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(静的)2 つの値が等しいかどうかをテストします。|  
  
## <a name="remarks"></a>コメント  
 この特徴 (traits) クラスを補足するため、`CSimpleMap`クラスです。 2 つを比較するためのメソッドを提供`CSimpleMap`要素 (具体的には、キーと値コンポーネント) の等価性のオブジェクトします。 既定では、キーと値が比較されます`operator==()`が必要な追加機能を提供するこのクラスをオーバーライドできますマップに、独自の等値演算子の複合データ型が含まれている場合。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>CSimpleMapEqualHelper::IsEqualKey  
 2 つのキーの等価性をテストします。  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>パラメーター  
 `k1`  
 最初のキー。  
  
 `k2`  
 2 番目のキー。  
  
### <a name="return-value"></a>戻り値  
 キーが等しい場合は false それ以外の場合は true を返します。  
  
##  <a name="isequalvalue"></a>CSimpleMapEqualHelper::IsEqualValue  
 2 つの値が等しいかどうかをテストします。  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>パラメーター  
 *v1*  
 最初の値。  
  
 *v2*  
 2 番目の値。  
  
### <a name="return-value"></a>戻り値  
 値が等しい場合は false それ以外の場合は true を返します。  
  
## <a name="see-also"></a>参照  
 [CSimpleMapEqualHelperFalse クラス](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
