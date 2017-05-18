---
title: "CAutoVectorPtrElementTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: d7b7418b713993f539f56e70715296d5af265d28
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cautovectorptrelementtraits-class"></a>CAutoVectorPtrElementTraits クラス
このクラスは、メソッド、静的関数、および新しいベクトルを使用して、スマート ポインターのコレクションを作成して、オペレーターを削除すると便利な typedef を提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CAutoVectorPtrElementTraits : 
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```    
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ポインター型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|  
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、スマート ポインターを含むコレクション クラスのオブジェクトを作成するときに役立つメソッド、静的関数、および typedef を提供します。 異なり[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)、このクラスの使用方法は、新しいベクトルし、オペレーターを削除します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoVectorPtrElementTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="inargtype"></a>CAutoVectorPtrElementTraits::INARGTYPE  
 コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。  
  
```
typedef CAutoVectorPtr<T>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CAutoVectorPtrElementTraits::OUTARGTYPE  
 コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。  
  
```
typedef T*& OUTARGTYPE;
```  
  
## <a name="see-also"></a>関連項目  
 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
 [出たリソース クラス](../../atl/reference/cautovectorptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

