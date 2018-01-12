---
title: "IWorkerThreadClient インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs: C++
helpviewer_keywords: IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86b0578b3fbe16d21a12edf2ac5eb91528419e83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient インターフェイス
`IWorkerThreadClient`クライアントによって実装されるインターフェイスは、[使用](../../atl/reference/cworkerthread-class.md)クラスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CloseHandle](#closehandle)|このオブジェクトに関連付けられたハンドルを終了するには、このメソッドを実装します。|  
|[実行します。](#execute)|このオブジェクトに関連付けられたハンドルがシグナル状態にコードを実行するには、このメソッドを実装します。|  
  
## <a name="remarks"></a>コメント  
 シグナル状態になるハンドルへの応答でワーカー スレッドで実行する必要があるコードがある場合は、このインターフェイスを実装します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlutil.h  
  
##  <a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 このオブジェクトに関連付けられたハンドルを終了するには、このメソッドを実装します。  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>パラメーター  
 *hHandle*  
 終了するハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、またはエラー発生時にエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドに渡されたハンドルはへの呼び出しによって、このオブジェクトに以前関連付けられていた[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)です。  
  
### <a name="example"></a>例  
 次のコードは、の簡単な実装を示しています。`IWorkerThreadClient::CloseHandle`です。  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="execute"></a>IWorkerThreadClient::Execute  
 このオブジェクトに関連付けられたハンドルがシグナル状態にコードを実行するには、このメソッドを実装します。  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwParam`  
 ユーザーのパラメーターです。  
  
 `hObject`  
 シグナル状態になるハンドルです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、またはエラー発生時にエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドに渡される DWORD/ポインター、ハンドルされたへの呼び出しでこのオブジェクトに既に関連付け[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)です。  
  
### <a name="example"></a>例  
 次のコードは、の簡単な実装を示しています。`IWorkerThreadClient::Execute`です。  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>参照  
 [クラス](../../atl/reference/atl-classes.md)   
 [CWorkerThread クラス](../../atl/reference/cworkerthread-class.md)
