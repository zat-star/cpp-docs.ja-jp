---
title: "CSimpleMapEqualHelperFalse クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSimpleMapEqualHelperFalse
- CSimpleMapEqualHelperFalse
- ATL.CSimpleMapEqualHelperFalse
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
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
ms.openlocfilehash: 68a08ffc0ba126c523a779e3d1a72217dead6235
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse クラス
このクラスは、ヘルパーを[CSimpleMap](../../atl/reference/csimplemap-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(静的)2 つのキーが等しいかどうかをテストします。|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(静的)False を返します。|  
  
## <a name="remarks"></a>コメント  
 この特徴 (traits) クラスを補足するため、`CSimpleMap`クラスです。 含まれる&2; つの要素を比較するためのメソッドを提供、`CSimpleMap`オブジェクト、値の要素を具体的には&2; つまたは&2; つの主要な要素です。  
  
 値の比較が常に false を返すし、さらが呼び出されます`ATLASSERT`これまで参照されている場合は false の引数を指定しています。 等値テストが十分に定義されていない場合、このクラスは、ほとんどのメソッドに正常に動作しなどの比較に依存するメソッドに対して適切に定義された形で失敗する可能性がキー/値ペアを含むマップ[:findval](../../atl/reference/csimplemap-class.md#findval)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpcoll.h  
  
##  <a name="a-nameisequalkeya--csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqualHelperFalse::IsEqualKey  
 2 つのキーが等しいかどうかをテストします。  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>パラメーター  
 `k1`  
 最初のキー。  
  
 `k2`  
 2 番目のキー。  
  
### <a name="return-value"></a>戻り値  
 キーが等しい場合、false の場合それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)します。  
  
##  <a name="a-nameisequalvaluea--csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqualHelperFalse::IsEqualValue  
 false を返します。  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>戻り値  
 false を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは常に false を返したしが呼び出されます`ATLASSERT`これまで参照されている場合は false の引数を指定しています。 目的は、`CSimpleMapEqualHelperFalse::IsEqualValue`は等しいかどうかテストが適切に定義されていないときに、適切に定義された方法で失敗する比較を使用する方法を強制することです。  
  
## <a name="see-also"></a>関連項目  
 [CSimpleMapEqualHelper クラス](../../atl/reference/csimplemapequalhelper-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

