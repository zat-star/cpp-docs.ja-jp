---
title: "コネクション ポイント グローバル関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
caps.latest.revision: 20
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
ms.openlocfilehash: 8271f512141e4d2cc274d180b31e1ad33bfc354e
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="connection-point-global-functions"></a>コネクション ポイント グローバル関数
これらの関数は、コネクション ポイントのサポートを提供し、シンク マップ。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に示されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。|  
|[AtlUnadvise](#atlunadvise)|通じて確立された接続を終了する`AtlAdvise`です。|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|アドバイズするか、イベント シンク マップのエントリ。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
   
##  <a name="atladvise"></a>AtlAdvise  
 オブジェクトのコネクション ポイントとクライアントのシンクとの間に接続を確立します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
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
 [in]クライアントへのポインター **IUnknown**します。  
  
 `iid`  
 [in]接続ポイントの GUID です。 通常、これは接続ポイントで管理するアウトゴーイング インターフェイスの場合と同じです。  
  
 `pdw`  
 [out]接続を一意に識別するクッキーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 シンクでは、接続ポイントでサポートされている着信インターフェイスを実装します。 クライアントを使用して、`pdw`に渡すことによって、接続を削除するクッキー [AtlUnadvise](#atlunadvise)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&91;](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="atlunadvise"></a>AtlUnadvise  
 通じて確立された接続を終了する[AtlAdvise](#atladvise)します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkCP`  
 [in]ポインター、 **IUnknown**オブジェクトと、クライアントが接続されているのです。  
  
 `iid`  
 [in]接続ポイントの GUID です。 通常、これは接続ポイントで管理するアウトゴーイング インターフェイスの場合と同じです。  
  
 `dw`  
 [in]接続を一意に識別するクッキー。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&96;](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="atladvisesinkmap"></a>AtlAdviseSinkMap  
 オブジェクトのシンク イベント マップのすべてのエントリをアドバイズするか、アドバイズを中止します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 [in]シンク マップを含んでいるオブジェクトへのポインター。  
  
 `bAdvise`  
 [in]**true**シンクのすべてのエントリがすることに注意している場合**false**場合、シンクのすべてのエントリをアドバイズを中止します。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&92;](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)   
 [コネクション ポイントに関するマクロ](../../atl/reference/connection-point-macros.md)

