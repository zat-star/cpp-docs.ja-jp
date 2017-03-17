---
title: "CComQIPtrElementTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
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
ms.openlocfilehash: d6405cc3ec04988d0e0d7dd9a98f22c271b3608d
ms.lasthandoff: 02/24/2017

---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits クラス
このクラスでは、メソッド、静的関数、および typedef 便利な COM インターフェイス ポインターのコレクションを作成するときに提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename I, const IID* piid=& __uuidof(I)>  
class CComQIPtrElementTraits : 
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```  
  
#### <a name="parameters"></a>パラメーター  
 `I`  
 格納されるポインターの型を指定する COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`I`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、メソッドを派生しのコレクション クラスを作成するときに便利な typedef を提供[CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM インターフェイス ポインターのオブジェクト。 このクラスは、両方で使用されて、 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md)と[CInterfaceList](../../atl/reference/cinterfacelist-class.md)クラスです。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="inargtype"></a>CComQIPtrElementTraits::INARGTYPE  
 コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。  
  
```
typedef I* INARGTYPE;
```  
  
## <a name="see-also"></a>関連項目  
 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

