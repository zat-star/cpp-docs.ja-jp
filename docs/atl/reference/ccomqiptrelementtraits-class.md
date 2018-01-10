---
title: "CComQIPtrElementTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
dev_langs: C++
helpviewer_keywords: CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 30d4e73f3c1e4ad75b8b33442be4e64af1a11207
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits クラス
このクラスは、COM インターフェイス ポインターのコレクションを作成するときに、メソッド、静的関数、および typedef 便利を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename I, const IID* piid=& __uuidof(I)>  
class CComQIPtrElementTraits : 
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```  
  
#### <a name="parameters"></a>パラメーター  
 `I`  
 格納するポインターの種類を指定する COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`I`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、メソッドを派生しのコレクション クラスを作成するときに、便利 typedef を提供[CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM インターフェイス ポインター オブジェクトです。 このクラスは、両方で使用される、 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md)と[CInterfaceList](../../atl/reference/cinterfacelist-class.md)クラスです。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="inargtype"></a>CComQIPtrElementTraits::INARGTYPE  
 コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。  
  
```
typedef I* INARGTYPE;
```  
  
## <a name="see-also"></a>参照  
 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
