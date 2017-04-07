---
title: "CThreadPool クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CThreadPool
- ATLUTIL/ATL::CThreadPool
- ATLUTIL/ATL::CThreadPool::CThreadPool
- ATLUTIL/ATL::CThreadPool::AddRef
- ATLUTIL/ATL::CThreadPool::GetNumThreads
- ATLUTIL/ATL::CThreadPool::GetQueueHandle
- ATLUTIL/ATL::CThreadPool::GetSize
- ATLUTIL/ATL::CThreadPool::GetTimeout
- ATLUTIL/ATL::CThreadPool::Initialize
- ATLUTIL/ATL::CThreadPool::QueryInterface
- ATLUTIL/ATL::CThreadPool::QueueRequest
- ATLUTIL/ATL::CThreadPool::Release
- ATLUTIL/ATL::CThreadPool::SetSize
- ATLUTIL/ATL::CThreadPool::SetTimeout
- ATLUTIL/ATL::CThreadPool::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
caps.latest.revision: 22
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
ms.openlocfilehash: 632514d03e7037ef42a1566462db5dec6f5cc1e5
ms.lasthandoff: 02/24/2017

---
# <a name="cthreadpool-class"></a>CThreadPool クラス
このクラスは、作業項目のキューを処理するワーカー スレッドのプールを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Worker, class ThreadTraits = DefaultThreadTraits>  
class CThreadPool : public IThreadPoolConfig
```  
  
#### <a name="parameters"></a>パラメーター  
 *作業者*  
 準拠するクラス、[ワーカー アーキタイプ](../../atl/reference/worker-archetype.md)項目は、スレッド プールのキューに置かれた作業の処理に使用するコードを提供します。  
  
 `ThreadTraits`  
 プール内のスレッドを作成するための関数を提供するクラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|スレッド プールのコンス トラクターです。|  
|[CThreadPool:: ~ CThreadPool](#dtor)|スレッド プールのデストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|実装`IUnknown::AddRef`します。|  
|[CThreadPool::GetNumThreads](#getnumthreads)|プールのスレッドの数を取得するには、このメソッドを呼び出します。|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|作業項目をキューに使用する IO 完了ポートのハンドルを取得するには、このメソッドを呼び出します。|  
|[CThreadPool::GetSize](#getsize)|プールのスレッドの数を取得するには、このメソッドを呼び出します。|  
|[CThreadPool::GetTimeout](#gettimeout)|シャット ダウンするスレッドのスレッド プールが待機するミリ秒単位で最大の時刻を取得するには、このメソッドを呼び出します。|  
|[CThreadPool::Initialize](#initialize)|このメソッドでは、スレッド プールを初期化します。|  
|[CThreadPool::QueryInterface](#queryinterface)|実装**:queryinterface**します。|  
|[CThreadPool::QueueRequest](#queuerequest)|プール内のスレッドで処理する作業アイテムをキューには、このメソッドを呼び出します。|  
|[CThreadPool::Release](#release)|実装`IUnknown::Release`します。|  
|[CThreadPool::SetSize](#setsize)|プールのスレッドの数を設定するには、このメソッドを呼び出します。|  
|[CThreadPool::SetTimeout](#settimeout)|シャット ダウンするスレッドのスレッド プールが待機するミリ秒単位で時間の最大値を設定するには、このメソッドを呼び出します。|  
|[CThreadPool::Shutdown](#shutdown)|スレッド プールをシャット ダウンするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 プール内のスレッドが作成され、プールが初期化されて、サイズ変更、またはシャット ダウン時に破棄されます。 クラスのインスタンス*ワーカー*プール内の各ワーカー スレッドのスタック上に作成されます。 各インスタンスがスレッドの有効期間にわたって有効です。  
  
 スレッドの作成後すぐに*ワーカー*::`Initialize`がそのスレッドに関連付けられているオブジェクトに対して呼び出されます。 スレッドの破棄する直前に*ワーカー*::`Terminate`が呼び出されます。 どちらのメソッドに渡す必要があります、 **void\* **引数。 この引数の値が使用中のスレッド プールに渡される、`pvWorkerParam`のパラメーター [CThreadPool::Initialize](#initialize)します。  
  
 ワーカー スレッドはキューの呼び出しからの項目をプルがある場合に作業項目のキューとワーカー スレッドの作業に使用できる、 **Execute**のメソッド、*ワーカー*そのスレッドのオブジェクト。 3 つの項目は、メソッドに渡されます。 同じキューからアイテム`pvWorkerParam`に渡される*ワーカー*::`Initialize`と*ワーカー*:: `Terminate`、とへのポインター、 [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) IO 完了ポートのキューに使用される構造です。  
  
 *ワーカー*クラスは、typedef、提供することにより、スレッド プールのキューに配置される項目の型を宣言して*ワーカー*::`RequestType`です。 この型との間にキャストできる必要があります、 **ULONG_PTR**します。  
  
 例、*ワーカー*クラスは[CNonStatelessWorker クラス](../../atl/reference/cnonstatelessworker-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="addref"></a>CThreadPool::AddRef  
 実装`IUnknown::AddRef`します。  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスは、参照カウントを使用した有効期間の制御を実装していません。  
  
##  <a name="cthreadpool"></a>CThreadPool::CThreadPool  
 スレッド プールのコンス トラクターです。  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>コメント  
 タイムアウトの値を初期化します[ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10)します。  
  
##  <a name="dtor"></a>CThreadPool:: ~ CThreadPool  
 スレッド プールのデストラクターです。  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し[CThreadPool::Shutdown](#shutdown)します。  
  
##  <a name="getnumthreads"></a>CThreadPool::GetNumThreads  
 プールのスレッドの数を取得するには、このメソッドを呼び出します。  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>戻り値  
 プールのスレッドの数を返します。  
  
##  <a name="getqueuehandle"></a>CThreadPool::GetQueueHandle  
 作業項目をキューに使用する IO 完了ポートのハンドルを取得するには、このメソッドを呼び出します。  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>戻り値  
 スレッド プールが初期化されていない場合は、キュー ハンドルまたは NULL を返します。  
  
##  <a name="getsize"></a>CThreadPool::GetSize  
 プールのスレッドの数を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pnNumThreads`  
 [out]成功した場合に、プールのスレッドの数を受け取る変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="gettimeout"></a>CThreadPool::GetTimeout  
 シャット ダウンするスレッドのスレッド プールが待機するミリ秒単位で最大の時刻を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pdwMaxWait`  
 [out]成功した場合に、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を受け取る変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このタイムアウト値を使って[CThreadPool::Shutdown](#shutdown)メソッドに他の値を指定しない場合。  
  
##  <a name="initialize"></a>CThreadPool::Initialize  
 このメソッドでは、スレッド プールを初期化します。  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pvWorkerParam`  
 ワーカー スレッドのオブジェクトに渡されるワーカー パラメーター `Initialize`、 **Execute**、および`Terminate`メソッドです。  
  
 `nNumThreads`  
 要求された、プール内のスレッド数。  
  
 場合`nNumThreads`は負の場合、その絶対値を掛けたスレッドの合計数を取得するマシンのプロセッサ数です。  
  
 場合`nNumThreads`0 の場合は、 [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571)スレッドの合計数を取得するマシンのプロセッサ数で乗算されます。  
  
 `dwStackSize`  
 プール内の各スレッドのスタック サイズ。  
  
 *hCompletion*  
 完了ポートに関連付けるオブジェクトのハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="queryinterface"></a>CThreadPool::QueryInterface  
 実装**:queryinterface**します。  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>コメント  
 このクラスのオブジェクトを正常な照会できる、 **IUnknown**と[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)インターフェイスです。  
  
##  <a name="queuerequest"></a>CThreadPool::QueueRequest  
 プール内のスレッドで処理する作業アイテムをキューには、このメソッドを呼び出します。  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `request`  
 キューに置かれた要求です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、作業項目をキューに追加します。 プール内のスレッドは、受信した順序でキューから項目を選択します。  
  
##  <a name="release"></a>CThreadPool::Release  
 実装`IUnknown::Release`します。  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスは、参照カウントを使用した有効期間の制御を実装していません。  
  
##  <a name="setsize"></a>CThreadPool::SetSize  
 プールのスレッドの数を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nNumThreads`  
 要求された、プール内のスレッド数。  
  
 場合`nNumThreads`は負の場合、その絶対値を掛けたスレッドの合計数を取得するマシンのプロセッサ数です。  
  
 場合`nNumThreads`0 の場合は、 [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571)スレッドの合計数を取得するマシンのプロセッサ数で乗算されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 指定されたスレッドの数が、プール内の現在のスレッドの数よりも小さい場合は、オブジェクトは、待機中のスレッドで取り上げられることにキューにシャット ダウン メッセージを格納します。 待機中のスレッドがキューからメッセージを取得、スレッド プールに通知して、スレッドのプロシージャを終了します。 プール内のスレッドの数が、指定した数に到達するまで、またはで指定された期間内のスレッドが終了していない、このプロセスが繰り返されます[GetTimeout](#gettimeout)/ [SetTimeout](#settimeout)します。 このような場合、メソッドに対応する HRESULT **WAIT_TIMEOUT**保留中のシャット ダウン メッセージが取り消されるとします。  
  
##  <a name="settimeout"></a>CThreadPool::SetTimeout  
 シャット ダウンするスレッドのスレッド プールが待機するミリ秒単位で時間の最大値を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMaxWait`  
 シャット ダウンするスレッドのスレッド プールが待機するミリ秒単位で要求の最大時間。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 タイムアウトに初期化[ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10)コンス トラクターでします。  
  
 注意`dwMaxWait`をシャット ダウンする単一のスレッドのプールが待機する時間です。 複数のスレッド プールから削除するを実行するまでの最大時間よりもやや少ない`dwMaxWait`スレッドの数を掛けた値します。  
  
##  <a name="shutdown"></a>CThreadPool::Shutdown  
 スレッド プールをシャット ダウンするには、このメソッドを呼び出します。  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMaxWait`  
 シャット ダウンするスレッドのスレッド プールが待機するミリ秒単位で要求の最大時間。 このメソッドが設定されたタイムアウトを使用して 0 または値を指定する場合[CThreadPool::SetTimeout](#settimeout)します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、プール内のすべてのスレッドをシャット ダウン要求を送信します。 このメソッドの呼び出しがタイムアウトになると、 [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717)終了しなかったすべてのスレッドでします。 このメソッドは、クラスのデストラクターから自動的に呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [IThreadPoolConfig インターフェイス](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [クラス](../../atl/reference/atl-classes.md)

