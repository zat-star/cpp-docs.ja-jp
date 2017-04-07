---
title: "CElementTraitsBase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
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
ms.openlocfilehash: a06af7698afb24c1c2391b762673c7e3633018d4
ms.lasthandoff: 02/24/2017

---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase クラス
このクラスは、既定のコピーを提供し、コレクション クラスのメソッドに移動します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>  
class CElementTraitsBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|  
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](#copyelements)|コレクション クラスのオブジェクトに格納されている要素をコピーするには、このメソッドを呼び出します。|  
|[CElementTraitsBase::RelocateElements](#relocateelements)|コレクション クラスのオブジェクトに格納されている要素を配置する場合に、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 この基本クラスでは、コピーして、コレクション クラス内の要素を再配置するためのメソッドを定義します。 クラスによって使用されて[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)、 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)、および[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)します。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="copyelements"></a>CElementTraitsBase::CopyElements  
 コレクション クラスのオブジェクトに格納されている要素をコピーするには、このメソッドを呼び出します。  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 コピー元のデータを受信する最初の要素へのポインター。  
  
 `pSrc`  
 コピーする最初の要素へのポインター。  
  
 `nElements`  
 コピーする要素の数。  
  
### <a name="remarks"></a>コメント  
 ソースおよびデスティネーションの要素は重複できません。  
  
##  <a name="inargtype"></a>CElementTraitsBase::INARGTYPE  
 データは、コレクションに要素を追加するために使用する型します。  
  
```
typedef const T& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE  
 コレクションから要素を取得するために使用するデータ型。  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CElementTraitsBase::RelocateElements  
 コレクション クラスのオブジェクトに格納されている要素を配置する場合に、このメソッドを呼び出します。  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 再配置されたデータを受信する最初の要素へのポインター。  
  
 `pSrc`  
 配置する場合に最初の要素へのポインター。  
  
 `nElements`  
 再配置する要素の数。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[memmove](../../c-runtime-library/reference/memmove-wmemmove.md)、これは、ほとんどのデータ型。 オブジェクトの移動中に、独自のメンバーへのポインターが含まれている場合は、このメソッドをオーバーライドする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

