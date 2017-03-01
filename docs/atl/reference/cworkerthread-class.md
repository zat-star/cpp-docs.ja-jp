---
title: "クラスの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CWorkerThread<ThreadTraits>
- ATL::CWorkerThread
- ATL.CWorkerThread
- ATL.CWorkerThread<ThreadTraits>
- CWorkerThread
dev_langs:
- C++
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
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
ms.openlocfilehash: ab1c92c1b7442025f91007ef971d81d087351212
ms.lasthandoff: 02/24/2017

---
# <a name="cworkerthread-class"></a>クラスの使用
このクラスは、ワーカー スレッドを作成または既存のものを使用して化し、1 つまたは複数のカーネル オブジェクトのハンドルを待機ハンドルのいずれかが通知された場合は、指定したクライアント関数を実行します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>パラメーター  
 `ThreadTraits`  
 など、スレッド作成関数を提供するクラス[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)または[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-structures"></a>保護されている構造体  
  
|名前|説明|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](#cworkerthread)|ワーカー スレッドのコンス トラクターです。|  
|[使用:: ~ 使用](#dtor)|ワーカー スレッドのデストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](#addhandle)|待機可能オブジェクトのハンドルをワーカー スレッドによって管理されるリストに追加するには、このメソッドを呼び出します。|  
|[CWorkerThread::AddTimer](#addtimer)|定期的な待機可能なタイマーをワーカー スレッドによって管理されるリストに追加するには、このメソッドを呼び出します。|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|ワーカー スレッドのスレッド ハンドルを取得するには、このメソッドを呼び出します。|  
|[CWorkerThread::GetThreadId](#getthreadid)|ワーカー スレッドのスレッド ID を取得するには、このメソッドを呼び出します。|  
|[CWorkerThread::Initialize](#initialize)|このメソッドでは、ワーカー スレッドを初期化します。|  
|[CWorkerThread::RemoveHandle](#removehandle)|ハンドルを待機可能オブジェクトの一覧から削除するには、このメソッドを呼び出します。|  
|[CWorkerThread::Shutdown](#shutdown)|ワーカー スレッドをシャット ダウンするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
  
### <a name="to-use-cworkerthread"></a>使用を使用するには  
  
1.  このクラスのインスタンスを作成します。  
  
2.  呼び出す[CWorkerThread::Initialize](#initialize)します。  
  
3.  呼び出す[CWorkerThread::AddHandle](#addhandle)カーネル オブジェクトとの実装へのポインターのハンドルを持つ[IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)します。  
  
     または  
  
     呼び出す[CWorkerThread::AddTimer](#addtimer)の実装へのポインターを[IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)します。  
  
4.  実装[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)ハンドルまたはタイマーがシグナル通知されたときに、何らかのアクションを実行します。  
  
5.  待機可能オブジェクトの一覧からオブジェクトを削除するには、呼び出す[CWorkerThread::RemoveHandle](#removehandle)します。  
  
6.  スレッドを終了するには、呼び出す[CWorkerThread::Shutdown](#shutdown)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="a-nameaddhandlea--cworkerthreadaddhandle"></a><a name="addhandle"></a>CWorkerThread::AddHandle  
 待機可能オブジェクトのハンドルをワーカー スレッドによって管理されるリストに追加するには、このメソッドを呼び出します。  
  
```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 待機可能オブジェクトへのハンドル。  
  
 `pClient`  
 ポインター、 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)ハンドルがシグナル通知されたときに呼び出されるオブジェクトのインターフェイスです。  
  
 `dwParam`  
 渡されるパラメーター [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)ハンドルがシグナル通知されたとき。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)を介して呼び出す`pClient`ときに、ハンドル`hObject`、通知されます。  
  
##  <a name="a-nameaddtimera--cworkerthreadaddtimer"></a><a name="addtimer"></a>CWorkerThread::AddTimer  
 定期的な待機可能なタイマーをワーカー スレッドによって管理されるリストに追加するには、このメソッドを呼び出します。  
  
```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwInterval*  
 タイマーの間隔をミリ秒単位で指定します。  
  
 `pClient`  
 ポインター、 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)ハンドルがシグナル通知されたときに呼び出されるオブジェクトのインターフェイスです。  
  
 `dwParam`  
 渡されるパラメーター [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)ハンドルがシグナル通知されたとき。  
  
 `phTimer`  
 [out]成功した場合、新しく作成したタイマーを識別するハンドルを受け取るハンドル変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)を介して呼び出す`pClient`タイマーが通知されます。  
  
 タイマーのハンドルを渡す`phTimer`に[CWorkerThread::RemoveHandle](#removehandle)タイマーを閉じます。  
  
##  <a name="a-namecworkerthreada--cworkerthreadcworkerthread"></a><a name="cworkerthread"></a>CWorkerThread::CWorkerThread  
 コンストラクターです。  
  
```
CWorkerThread() throw();
```  
  
##  <a name="a-namedtora--cworkerthreadcworkerthread"></a><a name="dtor"></a>使用:: ~ 使用  
 デストラクターです。  
  
```
~CWorkerThread() throw();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し[CWorkerThread::Shutdown](#shutdown)します。  
  
##  <a name="a-namegetthreadhandlea--cworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CWorkerThread::GetThreadHandle  
 ワーカー スレッドのスレッド ハンドルを取得するには、このメソッドを呼び出します。  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ワーカー スレッドが初期化されていない場合は、スレッド ハンドルまたは NULL を返します。  
  
##  <a name="a-namegetthreadida--cworkerthreadgetthreadid"></a><a name="getthreadid"></a>CWorkerThread::GetThreadId  
 ワーカー スレッドのスレッド ID を取得するには、このメソッドを呼び出します。  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ワーカー スレッドが初期化されていない場合は、スレッド ID または NULL を返します。  
  
##  <a name="a-nameinitializea--cworkerthreadinitialize"></a><a name="initialize"></a>CWorkerThread::Initialize  
 このメソッドでは、ワーカー スレッドを初期化します。  
  
```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pThread`  
 既存のワーカー スレッドです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、作成後またはへの呼び出し後、オブジェクトを初期化するために呼び出す必要があります[CWorkerThread::Shutdown](#shutdown)します。  
  
 2 つ以上の`CWorkerThread`オブジェクトが同じワーカー スレッドを使用して、任意の引数は、オブジェクトを指すポインターを渡す渡されずのいずれかの初期化、`Initialize`他の方法です。 ポインターを使用して初期化されたオブジェクトは、オブジェクトの初期化に使用する前にシャット ダウンする必要があります。  
  
 参照してください[CWorkerThread::Shutdown](#shutdown)については、既存のオブジェクトへのポインターを使用して初期化されるときに、そのメソッドの動作がどのように変化するかをします。  
  
##  <a name="a-nameremovehandlea--cworkerthreadremovehandle"></a><a name="removehandle"></a>CWorkerThread::RemoveHandle  
 ハンドルを待機可能オブジェクトの一覧から削除するには、このメソッドを呼び出します。  
  
```
HRESULT RemoveHandle(HANDLE hObject) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 削除するハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 ハンドルが削除されたとき[IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle)に渡された関連付けられているオブジェクトで呼び出される[AddHandle](#addhandle)します。 この呼び出しが失敗した場合、 `CWorkerThread` 、Windows を呼び出す[CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211)処理関数です。  
  
##  <a name="a-nameshutdowna--cworkerthreadshutdown"></a><a name="shutdown"></a>CWorkerThread::Shutdown  
 ワーカー スレッドをシャット ダウンするには、このメソッドを呼び出します。  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwWait`  
 ワーカー スレッドをシャット ダウンするを待機するミリ秒単位の時間。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、または失敗した場合の場合など、エラーの hresult 値は S_OK を返しますタイムアウト値`dwWait`を超過します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトを再利用する[CWorkerThread::Initialize](#initialize)このメソッドを呼び出した後。  
  
 呼び出して**シャット ダウン**別にポインターを使用して初期化されるオブジェクトに`CWorkerThread`オブジェクトも何も起こりません、常に S_OK を返します。  
  
## <a name="see-also"></a>関連項目  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [クラス](../../atl/reference/atl-classes.md)   
 [マルチ スレッド: ワーカー スレッドの生成](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient インターフェイス](../../atl/reference/iworkerthreadclient-interface.md)

