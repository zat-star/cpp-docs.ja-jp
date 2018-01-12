---
title: "CInterfaceArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
dev_langs: C++
helpviewer_keywords: CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ece9858d0be171febaeb52e820e922665ac2a351
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cinterfacearray-class"></a>CInterfaceArray クラス
このクラスは、COM インターフェイス ポインターの配列を構築するときに役立つメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>パラメーター  
 `I`  
 格納するポインターの種類を指定する COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`I`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|インターフェイスの配列のコンス トラクターです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、コンス トラクターおよび COM インターフェイス ポインターの配列を作成するための派生メソッドを提供します。 使用して[CInterfaceList](../../atl/reference/cinterfacelist-class.md)リストが必要な場合です。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="cinterfacearray"></a>CInterfaceArray::CInterfaceArray  
 コンストラクターです。  
  
```
CInterfaceArray() throw();
```  
  
### <a name="remarks"></a>コメント  
 スマート ポインターの配列を初期化します。  
  
## <a name="see-also"></a>参照  
 [CAtlArray クラス](../../atl/reference/catlarray-class.md)   
 [CComQIPtr クラス](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits クラス](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
