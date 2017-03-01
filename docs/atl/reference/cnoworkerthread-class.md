---
title: "CNoWorkerThread クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CNoWorkerThread
- ATL.CNoWorkerThread
- CNoWorkerThread
dev_langs:
- C++
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
caps.latest.revision: 21
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
ms.openlocfilehash: 4c38d778849a31d55a657fc1022c2e9f4a370eec
ms.lasthandoff: 02/24/2017

---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread クラス
引数としてこのクラスを使用して、`MonitorClass`動的キャッシュ管理を無効にする場合はキャッシュ クラスをテンプレート パラメーター。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CNoWorkerThread
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CNoWorkerThread::AddHandle](#addhandle)|同等の非機能[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。|  
|[CNoWorkerThread::AddTimer](#addtimer)|同等の非機能[CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)します。|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|同等の非機能[CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)します。|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|同等の非機能[CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)します。|  
|[CNoWorkerThread::Initialize](#initialize)|同等の非機能[CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)します。|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|同等の非機能[CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)します。|  
|[CNoWorkerThread::Shutdown](#shutdown)|同等の非機能[CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)します。|  
  
## <a name="remarks"></a>コメント  
 このクラスと同じパブリック インターフェイスを提供する[使用](../../atl/reference/cworkerthread-class.md)します。 提供するこのインターフェイスが予期される、`MonitorClass`キャッシュ クラスをテンプレート パラメーター。  
  
 このクラスのメソッドを実装して、何も行いません。 常に HRESULT を返すメソッドは、S_OK を返すし、常に、ハンドルまたはスレッドの ID を返すメソッドは、0 を返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="a-nameaddhandlea--cnoworkerthreadaddhandle"></a><a name="addhandle"></a>CNoWorkerThread::AddHandle  
 同等の非機能[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。  
  
```
HRESULT AddHandle(HANDLE /* hObject
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供されている実装では、何も行いません。  
  
##  <a name="a-nameaddtimera--cnoworkerthreadaddtimer"></a><a name="addtimer"></a>CNoWorkerThread::AddTimer  
 同等の非機能[CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)します。  
  
```
HRESULT AddTimer(DWORD /* dwInterval
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */,
    HANDLE* /* phTimer
 */) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供されている実装では、何も行いません。  
  
##  <a name="a-namegetthreadhandlea--cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CNoWorkerThread::GetThreadHandle  
 同等の非機能[CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)します。  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に NULL が返されます。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供されている実装では、何も行いません。  
  
##  <a name="a-namegetthreadida--cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a>CNoWorkerThread::GetThreadId  
 同等の非機能[CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)します。  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供されている実装では、何も行いません。  
  
##  <a name="a-nameinitializea--cnoworkerthreadinitialize"></a><a name="initialize"></a>CNoWorkerThread::Initialize  
 同等の非機能[CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)します。  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供されている実装では、何も行いません。  
  
##  <a name="a-nameremovehandlea--cnoworkerthreadremovehandle"></a><a name="removehandle"></a>CNoWorkerThread::RemoveHandle  
 同等の非機能[CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)します。  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供されている実装では、何も行いません。  
  
##  <a name="a-nameshutdowna--cnoworkerthreadshutdown"></a><a name="shutdown"></a>CNoWorkerThread::Shutdown  
 同等の非機能[CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)します。  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供されている実装では、何も行いません。

