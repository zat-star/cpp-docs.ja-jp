---
title: "入力したコネクション クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 81a68cae1d961f2846c1a807432f22ae92ca3b89
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="iconnectionpointcontainerimpl-class"></a>入力したコネクション クラス
このクラスは実装のコレクションを管理するための接続ポイント コンテナー [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IConnectionPointContainerImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|接続可能オブジェクトでサポートされている接続ポイントを反復処理する列挙子を作成します。|  
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|指定の IID をサポートする接続ポイントへのインターフェイス ポインターを取得します。|  
  
## <a name="remarks"></a>コメント  
 `IConnectionPointContainerImpl`実装のコレクションを管理するための接続ポイント コンテナー [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)オブジェクトです。 `IConnectionPointContainerImpl`詳細については、接続可能オブジェクトを取得するクライアントが呼び出すことができる&2; つの方法があります。  
  
- `EnumConnectionPoints`クライアントは、オブジェクトがサポートするどの送信インターフェイスを決定できます。  
  
- `FindConnectionPoint`クライアントは、オブジェクトが特定の送信インターフェイスをサポートするかどうかを確認できます。  
  
 ATL でのコネクション ポイントを使用する方法については、記事を参照して[コネクション ポイント](../../atl/atl-connection-points.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="enumconnectionpoints"></a>IConnectionPointContainerImpl::EnumConnectionPoints  
 接続可能オブジェクトでサポートされている接続ポイントを反復処理する列挙子を作成します。  
  
```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IConnectionPointContainer::EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="findconnectionpoint"></a>IConnectionPointContainerImpl::FindConnectionPoint  
 指定の IID をサポートする接続ポイントへのインターフェイス ポインターを取得します。  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [クラスの概要](../../atl/atl-class-overview.md)

