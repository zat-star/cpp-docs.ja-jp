---
title: "CSimpleArrayEqualHelper クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57e5b40785bda57a4d5578bb998c4c97336246be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper クラス
このクラスは、のヘルパー、 [CSimpleArray](../../atl/reference/csimplearray-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CSimpleArrayEqualHelper
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(静的)2 つのテスト`CSimpleArray`object 要素が等しいかどうか。|  
  
## <a name="remarks"></a>コメント  
 この特徴 (traits) クラスを補足するため、`CSimpleArray`クラスです。 格納されている 2 つの要素を比較するためにメソッドを提供する`CSimpleArray`オブジェクト。 既定では、要素を使用して比較**operator=()**配列には、独自の等値演算子の複合データ型が含まれています、このクラスをオーバーライドする必要があります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelper::IsEqual  
 2 つのテスト`CSimpleArray`object 要素が等しいかどうか。  
  
```
static bool IsEqual(
    const T& t1,
    const T& t2);
```  
  
### <a name="parameters"></a>パラメーター  
 *t1*  
 T 型のオブジェクト  
  
 *t2*  
 T 型のオブジェクト  
  
### <a name="return-value"></a>戻り値  
 要素が等しい場合は false それ以外の場合は true を返します。  
  
## <a name="see-also"></a>参照  
 [CSimpleArray クラス](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse クラス](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
