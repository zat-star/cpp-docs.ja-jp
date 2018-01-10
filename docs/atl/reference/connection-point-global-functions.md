---
title: "接続ポイントのグローバル関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
dev_langs: C++
helpviewer_keywords: connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce7f6fc3d2a0b51f88952dd720955367b1dfe9d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="connection-point-global-functions"></a>接続ポイントのグローバル関数
これらの関数は、接続ポイントのサポートを提供し、シンク マップ。  
  
> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。|  
|[AtlUnadvise](#atlunadvise)|通じて確立された接続を終了する`AtlAdvise`です。|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|アドバイズするか、イベント シンク マップのエントリ。|  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  
   
##  <a name="atladvise"></a>AtlAdvise  
 オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkCP`  
 [in]ポインター、 **IUnknown**オブジェクトのクライアントが接続ましょう。  
  
 *pUnk*  
 [in]クライアントへのポインター **IUnknown**です。  
  
 `iid`  
 [in]接続ポイントの GUID です。 通常、これは、接続ポイントによって管理されている着信インターフェイスと同じです。  
  
 `pdw`  
 [out]接続を一意に識別するクッキーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 シンクでは、接続ポイントでサポートされている着信インターフェイスを実装します。 クライアントを使用して、`pdw`に渡すことによって、接続を削除する cookie [AtlUnadvise](#atlunadvise)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="atlunadvise"></a>AtlUnadvise  
 通じて確立された接続を終了する[AtlAdvise](#atladvise)です。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkCP`  
 [in]ポインター、 **IUnknown**のクライアントが接続しているオブジェクト。  
  
 `iid`  
 [in]接続ポイントの GUID です。 通常、これは、接続ポイントによって管理されている着信インターフェイスと同じです。  
  
 `dw`  
 [in]接続を一意に識別するクッキー。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="atladvisesinkmap"></a>AtlAdviseSinkMap  
 オブジェクトのシンク イベント マップのすべてのエントリをアドバイズするか、アドバイズを中止します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 [in]シンク マップを含むオブジェクトへのポインター。  
  
 `bAdvise`  
 [in]**true**シンクのすべてのエントリをアドバイズする場合**false**シンクのすべてのエントリは、アドバイズを中止する場合。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>参照  
 [関数](../../atl/reference/atl-functions.md)   
 [接続ポイントに関するマクロ](../../atl/reference/connection-point-macros.md)
