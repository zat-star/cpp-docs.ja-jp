---
title: "IWorkerThreadClient インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2127d13dc11edb353ef27396f3457dd9abdc4a99
ms.lasthandoff: 02/24/2017

---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient インターフェイス
`IWorkerThreadClient`クライアントによって実装されるインターフェイスは、[使用](../../atl/reference/cworkerthread-class.md)クラスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
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
 シグナル状態になるハンドルへの応答のワーカー スレッド上で実行する必要があるコードがあるときは、このインターフェイスを実装します。  
  
## <a name="requirements"></a>要件  
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
 成功した場合、または失敗に関するエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドに渡されるハンドルがへの呼び出しで既にこのオブジェクトとの関連付けられている[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。  
  
### <a name="example"></a>例  
 次のコードの単純な実装を示しています。`IWorkerThreadClient::CloseHandle`します。  
  
 [!code-cpp[NVC_ATL_Utilities #&135;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="execute"></a>IWorkerThreadClient::Execute  
 このオブジェクトに関連付けられたハンドルがシグナル状態にコードを実行するには、このメソッドを実装します。  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwParam`  
 ユーザーのパラメーターです。  
  
 `hObject`  
 このハンドルは、シグナル状態になっています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、または失敗に関するエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 ハンドルおよび DWORD/へのポインターのこのメソッドに渡される以前に関連付けられていたこのオブジェクトへの呼び出しによって[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。  
  
### <a name="example"></a>例  
 次のコードの単純な実装を示しています。`IWorkerThreadClient::Execute`します。  
  
 [!code-cpp[NVC_ATL_Utilities #&136;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/atl-classes.md)   
 [クラスの使用](../../atl/reference/cworkerthread-class.md)

