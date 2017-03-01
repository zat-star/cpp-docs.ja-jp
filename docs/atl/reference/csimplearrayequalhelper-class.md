---
title: "CSimpleArrayEqualHelper クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: 19
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4a87879683257c66de5fe4e720dd29fa4c47031d
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper クラス
このクラスは、ヘルパーを[CSimpleArray](../../atl/reference/csimplearray-class.md)クラスです。  
  
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
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(静的)2 つのテスト`CSimpleArray`オブジェクトの要素が等しいかどうか。|  
  
## <a name="remarks"></a>コメント  
 この特徴 (traits) クラスを補足するため、`CSimpleArray`クラスです。 格納された&2; つの要素を比較するは、メソッドを提供する`CSimpleArray`オブジェクトです。 既定では、要素を使用して比較**operator=()**配列に、独自の等値演算子に関連付けられていない複合データ型が含まれている場合は、このクラスをオーバーライドする必要がありますが、します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpcoll.h  
  
##  <a name="a-nameisequala--csimplearrayequalhelperisequal"></a><a name="isequal"></a>CSimpleArrayEqualHelper::IsEqual  
 2 つのテスト`CSimpleArray`オブジェクトの要素が等しいかどうか。  
  
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
 要素が false でそれ以外の場合、等しい場合は true を返します。  
  
## <a name="see-also"></a>関連項目  
 [CSimpleArray クラス](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse クラス](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

