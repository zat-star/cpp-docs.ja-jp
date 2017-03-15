---
title: "CSimpleArrayEqualHelperFalse クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CSimpleArrayEqualHelperFalse<T>
- ATL::CSimpleArrayEqualHelperFalse
- ATL.CSimpleArrayEqualHelperFalse
- ATL::CSimpleArrayEqualHelperFalse<T>
- CSimpleArrayEqualHelperFalse
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: cd5ed7058194880ef1ceaebe788e3deb60d4ac8e
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse クラス
このクラスは、ヘルパーを[CSimpleArray](../../atl/reference/csimplearray-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(静的)False を返します。|  
  
## <a name="remarks"></a>コメント  
 この特徴 (traits) クラスを補完するは、`CSimpleArray`クラスです。 返します。 false、およびさらに、呼び出す常に it`ATLASSERT`これまで参照されている場合は false の引数を指定しています。 等値テストが十分に定義されていない場合、このクラスは、ほとんどのメソッドに正常に動作しなどの比較に依存するメソッドに対して適切に定義された形で失敗する可能性が要素を含む配列[CSimpleArray::Find](../../atl/reference/csimplearray-class.md#find)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpcoll.h  
  
##  <a name="a-nameisequala--csimplearrayequalhelperfalseisequal"></a><a name="isequal"></a>CSimpleArrayEqualHelperFalse::IsEqual  
 false を返します。  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>戻り値  
 false を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは常に false を返したしが呼び出されます`ATLASSERT`参照されている場合は false の引数を指定しています。 目的は、`CSimpleArrayEqualHelperFalse::IsEqual`は等しいかどうかテストが適切に定義されていないときに、適切に定義された方法で失敗する比較を使用する方法を強制することです。  
  
## <a name="see-also"></a>関連項目  
 [CSimpleArrayEqualHelper クラス](../../atl/reference/csimplearrayequalhelper-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

