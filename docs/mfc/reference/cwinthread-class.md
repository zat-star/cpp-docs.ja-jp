---
title: "CWinThread クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinThread
dev_langs:
- C++
helpviewer_keywords:
- worker threads
- threading [MFC], safety
- CWinThread class
- threading [MFC], creating threads
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
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
ms.openlocfilehash: 866e847f9c1d73d6f9882e50b1274fbad9e21a39
ms.lasthandoff: 02/24/2017

---
# <a name="cwinthread-class"></a>CWinThread クラス
アプリケーション内の実行中のスレッドを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWinThread::CWinThread](#cwinthread)|`CWinThread` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Cwinthread::createthread](#createthread)|実行を開始、`CWinThread`オブジェクトです。|  
|[CWinThread::ExitInstance](#exitinstance)|スレッドの終了時にクリーンアップするためにオーバーライドします。|  
|[CWinThread::GetMainWnd](#getmainwnd)|スレッドのメイン ウィンドウへのポインターを取得します。|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|現在のスレッドの優先度を取得します。|  
|[CWinThread::InitInstance](#initinstance)|スレッドのインスタンスを初期化するためにオーバーライドします。|  
|[CWinThread::IsIdleMessage](#isidlemessage)|特別なメッセージを確認します。|  
|[CWinThread::OnIdle](#onidle)|スレッド固有のアイドル状態時の処理を実行するためにオーバーライドします。|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|別のメッセージをポスト`CWinThread`オブジェクトです。|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Windows の関数にディスパッチされる前にメッセージをフィルター処理[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)します。|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|アプリケーションに到達する前に、特定のメッセージを受け取ります。|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|スレッドのメッセージとコマンド ハンドラーによってスローされたすべてのハンドルされない例外を受け取ります。|  
|[CWinThread::PumpMessage](#pumpmessage)|スレッドのメッセージ ループが含まれています。|  
|[Cwinthread::resumethread](#resumethread)|スレッドのデクリメントは、カウントを中断します。|  
|[CWinThread::Run](#run)|メッセージ ポンプを持つスレッドを制御する関数です。 既定のメッセージ ループをカスタマイズするためにオーバーライドします。|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|現在のスレッドの優先順位を設定します。|  
|[CWinThread::SuspendThread](#suspendthread)|スレッドのインクリメントでは、カウントを中断します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CWinThread::operator ハンドル](#operator_handle)|ハンドルを取得、`CWinThread`オブジェクトです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|スレッドの終了時のオブジェクトを破棄するかどうかを指定します。|  
|[CWinThread::m_hThread](#m_hthread)|現在のスレッドへのハンドルします。|  
|[CWinThread::m_nThreadID](#m_nthreadid)|現在のスレッドの ID です。|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|OLE サーバーがアクティブである場合は、コンテナー アプリケーションのメイン ウィンドウへのポインター。|  
|[ため](#m_pmainwnd)|アプリケーションのメイン ウィンドウへのポインターを保持します。|  
  
## <a name="remarks"></a>コメント  
 実行のメイン スレッドがから派生したオブジェクトによって提供される通常`CWinApp`です。`CWinApp`から派生した`CWinThread`します。 追加`CWinThread`オブジェクトは、特定のアプリケーションで複数のスレッドを使用します。  
  
 2 つの一般的な種類のスレッドがあるを`CWinThread`をサポートしています: ワーカー スレッドとユーザー インターフェイス スレッドです。 ワーカー スレッドがメッセージ ポンプを持っていない。 たとえば、スプレッドシート アプリケーションでバック グラウンド計算を実行するスレッドです。 ユーザー インターフェイス スレッドのメッセージ ポンプがあり、システムから受信したメッセージを処理します。 [CWinApp](../../mfc/reference/cwinapp-class.md)し、そこから派生したクラスは、ユーザー インターフェイス スレッドの例を示します。 他のユーザー インターフェイス スレッドから直接派生させることも`CWinThread`です。  
  
 クラスのオブジェクト`CWinThread`通常のスレッドの間存在します。 この動作を変更する場合は、設定[m_bAutoDelete](#m_bautodelete)に**FALSE**します。  
  
 `CWinThread`クラスはスレッド セーフなコードと MFC を実現に必要です。 スレッド固有の情報を維持するためにフレームワークによって使用されるスレッド ローカル データが管理`CWinThread`オブジェクトです。 この依存のための`CWinThread`スレッド ローカル データを処理するためには、MFC で MFC を使用する任意のスレッドを作成します。 ランタイム関数によって作成されたスレッドなど[_beginthread、_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) MFC Api を使用することはできません。  
  
 スレッドを作成するには[AfxBeginThread](application-information-and-management.md#afxbeginthread)します。 ワーカー ロールまたはユーザー インターフェイス スレッドをするかどうかに応じて、次の&2; つの形式があります。 ユーザー インターフェイス スレッドを実行する場合に、渡す`AfxBeginThread`へのポインター、`CRuntimeClass`の`CWinThread`-クラスを派生します。 ワーカー スレッドを作成する場合に渡される`AfxBeginThread`制御関数と、制御関数にパラメーターへのポインター。 ワーカー スレッドとユーザー インターフェイス スレッドの両方で、優先度、スタックのサイズ、作成フラグ、およびセキュリティ属性を変更するオプションのパラメーターを指定できます。 `AfxBeginThread`新しいへのポインターを返しますが`CWinThread`オブジェクトです。  
  
 呼び出す代わりに`AfxBeginThread`、構築することができます、 `CWinThread`- オブジェクトを派生`CreateThread`します。 この次の&2; 段階の構築方法を再利用する場合に便利ですが、`CWinThread`一連の作成とスレッド実行の終了間のオブジェクト。  
  
 詳細については`CWinThread`、記事を参照して[C++ と MFC を使用するマルチ スレッド](../../parallel/multithreading-with-cpp-and-mfc.md)、[マルチ スレッド: ユーザー インターフェイス スレッドの作成](../../parallel/multithreading-creating-user-interface-threads.md)、[マルチ スレッド: ワーカー スレッドの作成](../../parallel/multithreading-creating-worker-threads.md)、および[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecreatethreada--cwinthreadcreatethread"></a><a name="createthread"></a>Cwinthread::createthread  
 呼び出し元プロセスのアドレス空間内で実行するスレッドを作成します。  
  
```  
BOOL CreateThread(
    DWORD dwCreateFlags = 0,  
    UINT nStackSize = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCreateFlags`  
 スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の&1; つを含めることができます。  
  
- **CREATE_SUSPENDED**中断カウントを&1; としてスレッドを開始します。 使用**CREATE_SUSPENDED**のメンバー データを初期化する場合、`CWinThread`などのオブジェクト[m_bAutoDelete](#m_bautodelete)またはスレッドが実行を開始する前に、派生クラスのメンバーです。 初期化が完了した後を使用して、 [cwinthread::resumethread](#resumethread)を実行しているスレッドを開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。  
  
- **0**作成後すぐにスレッドを開始します。  
  
 `nStackSize`  
 新しいスレッドへのスタックのバイト サイズを指定します。 場合**0**、スタック サイズの既定値は、プロセスのプライマリ スレッドのものと同じサイズです。  
  
 `lpSecurityAttrs`  
 指す、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)をスレッドのセキュリティ属性を指定します。  
  
### <a name="return-value"></a>戻り値  
 スレッドが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`AfxBeginThread`スレッド オブジェクトを作成し、1 つの手順で実行します。 使用`CreateThread`作成とスレッド実行の終了の間にスレッド オブジェクトを再利用する場合。  
  
##  <a name="a-namecwinthreada--cwinthreadcwinthread"></a><a name="cwinthread"></a>CWinThread::CWinThread  
 `CWinThread` オブジェクトを構築します。  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>コメント  
 スレッドの実行を開始する、 [CreateThread](#createthread)メンバー関数。 呼び出してスレッドを作成したは通常[AfxBeginThread](http://msdn.microsoft.com/library/e9e8684d-24f7-4599-8fdf-1f4f560a753b)、どのこのコンス トラクターを呼び出し、および`CreateThread`です。  
  
##  <a name="a-nameexitinstancea--cwinthreadexitinstance"></a><a name="exitinstance"></a>CWinThread::ExitInstance  
 ほとんどオーバーライド内からフレームワークによって呼び出されます[実行](#run)、スレッドのこのインスタンスを終了するメンバー関数への呼び出しまたは[InitInstance](#initinstance)が失敗しました。  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>戻り値  
 スレッドの終了コード。0 なし、エラーを示し、エラーを示す 0 より大きい値です。 この値は、呼び出すことによって取得できる[GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要はありません、このメンバー関数どこからでも、内部、**実行**メンバー関数。 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。  
  
 この関数の既定の実装の削除、`CWinThread`オブジェクトの場合[m_bAutoDelete](#m_bautodelete)は**TRUE**します。 スレッドの終了時にその他のクリーンアップを実行する場合は、この関数をオーバーライドします。 実装`ExitInstance`コードが実行された後に、基本クラスのバージョンを呼び出す必要があります。  
  
##  <a name="a-namegetmainwnda--cwinthreadgetmainwnd"></a><a name="getmainwnd"></a>CWinThread::GetMainWnd  
 アプリケーションが OLE サーバーである場合は、直接参照することではなくアプリケーションのアクティブなメイン ウィンドウへのポインターを取得するには、この関数を呼び出して、`m_pMainWnd`アプリケーション オブジェクトのメンバーです。  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>戻り値  
 この関数は、windows の&2; 種類のいずれかにポインターを返します。 この関数が返すかどうか、スレッドが OLE サーバーの一部で、アクティブなコンテナー内の場所で有効になっているオブジェクトが存在し、[先](../../mfc/reference/cwinapp-class.md#m_pactivewnd)のデータ メンバー、`CWinThread`オブジェクトです。  
  
 この関数が返すコンテナー内の場所で有効になっているオブジェクトが存在しないか、アプリケーションが OLE サーバーではない、 [m_pMainWnd](#m_pmainwnd)スレッド オブジェクトのデータ メンバーです。  
  
### <a name="remarks"></a>コメント  
 これは直接参照することと同じユーザー インターフェイス スレッドの場合、`m_pActiveWnd`アプリケーション オブジェクトのメンバーです。  
  
 開発中のアプリケーションが OLE サーバーではない場合は、この関数を呼び出すことは、アプリケーション オブジェクトの `m_pMainWnd` メンバーを直接参照することと同じです。  
  
 既定の動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="a-namegetthreadprioritya--cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a>CWinThread::GetThreadPriority  
 このスレッドの現在のスレッド優先順位を取得します。  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>戻り値  
 優先度クラス内で現在のスレッドの優先順位レベルです。 返される値は、次のいずれかを指定が優先度の高い順に一覧表示します。  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 これらの優先順位の詳細については、次を参照してください。 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameinitinstancea--cwinthreadinitinstance"></a><a name="initinstance"></a>CWinThread::InitInstance  
 `InitInstance`ユーザー インターフェイス スレッドの新しいインスタンスを初期化するためにオーバーライドする必要があります。  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常をオーバーライドする`InitInstance`スレッドが最初に作成したときに実行しなければならないタスクを実行します。  
  
 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。 制御関数に渡されるにおいてワーカー スレッドの初期化を実行[AfxBeginThread](application-information-and-management.md#afxbeginthread)します。  
  
##  <a name="a-nameisidlemessagea--cwinthreadisidlemessage"></a><a name="isidlemessage"></a>CWinThread::IsIdleMessage  
 保持するには、この関数をオーバーライド**OnIdle**特定のメッセージが生成された後に呼び出されるからです。  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 処理されている現在のメッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`OnIdle`処理後に呼び出す必要があります。 それ以外の場合 0 がメッセージです。  
  
### <a name="remarks"></a>コメント  
 既定の実装は呼び出しません**OnIdle**冗長なマウス メッセージおよびメッセージのキャレットの点滅によって生成された後です。  
  
 アプリケーションは、短い時間のタイマーを作成した場合**OnIdle**呼び出される多くの場合、パフォーマンスの問題が発生します。 このようなアプリケーションのパフォーマンスを向上させるためにオーバーライド`IsIdleMessage`アプリケーションの`CWinApp`-をチェックするクラスを派生`WM_TIMER`メッセージを次のようにします。  
  
 [!code-cpp[NVC_MFCDocView #&189;](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 処理`WM_TIMER`この方法では短いタイマーを使用するアプリケーションのパフォーマンスが向上します。  
  
##  <a name="a-namembautodeletea--cwinthreadmbautodelete"></a><a name="m_bautodelete"></a>CWinThread::m_bAutoDelete  
 スレッドの終了時に `CWinThread` オブジェクトを自動的に削除するかどうかを指定します。  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>コメント  
 `m_bAutoDelete`データ メンバーは型のパブリック変数**BOOL**します。  
  
 `m_bAutoDelete` の値は、基になるスレッド ハンドルを閉じる方法に影響しません。 スレッド ハンドルは、`CWinThread` オブジェクトが破棄されるときに必ず閉じられます。  
  
##  <a name="a-namemhthreada--cwinthreadmhthread"></a><a name="m_hthread"></a>CWinThread::m_hThread  
 これに接続されているスレッドへのハンドル`CWinThread`します。  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hThread`データ メンバーは型のパブリック変数`HANDLE`します。 基になるスレッドを現在存在する場合にのみ有効です。  
  
##  <a name="a-namemnthreadida--cwinthreadmnthreadid"></a><a name="m_nthreadid"></a>CWinThread::m_nThreadID  
 スレッドの ID は、これに接続されている`CWinThread`します。  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>コメント  
 **M_nThreadID**データ メンバーは型のパブリック変数`DWORD`します。 基になるスレッドを現在存在する場合にのみ有効です。  
  
### <a name="example"></a>例  
  例を参照してください[AfxGetThread](application-information-and-management.md#afxgetthread)します。  
  
##  <a name="a-namempactivewnda--cwinthreadmpactivewnd"></a><a name="m_pactivewnd"></a>CWinThread::m_pActiveWnd  
 このデータ メンバーを使用すると、スレッドのアクティブなウィンドウ オブジェクトへのポインターを格納できます。  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>コメント  
 Microsoft Foundation Class ライブラリは、ウィンドウがによって参照される場合、スレッド終了自動的に`m_pActiveWnd`が閉じられます。 このスレッドは、アプリケーションのプライマリ スレッドは、アプリケーションも終了します。 このデータ メンバーの場合**NULL**、アプリケーションのアクティブなウィンドウ`CWinApp`はオブジェクトが継承されます。 `m_pActiveWnd`型のパブリック変数**CWnd\***します。  
  
 オーバーライドする場合にこのメンバー変数を設定する通常、`InitInstance`です。 ワーカー スレッドでは、このデータ メンバーの値は親スレッドから継承されます。  
  
##  <a name="a-namempmainwnda--cwinthreadmpmainwnd"></a><a name="m_pmainwnd"></a>ため  
 このデータ メンバーを使用すると、スレッドのメイン ウィンドウのオブジェクトへのポインターを格納できます。  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>コメント  
 Microsoft Foundation Class ライブラリは、ウィンドウがによって参照される場合、スレッド終了自動的に`m_pMainWnd`が閉じられます。 このスレッドは、アプリケーションのプライマリ スレッドは、アプリケーションも終了します。 このデータ メンバーの場合**NULL**、アプリケーションのメイン ウィンドウ`CWinApp`オブジェクトを使用してスレッドを終了するタイミングを決定します。 `m_pMainWnd`型のパブリック変数**CWnd\***します。  
  
 オーバーライドする場合にこのメンバー変数を設定する通常、`InitInstance`です。 ワーカー スレッドでは、このデータ メンバーの値は親スレッドから継承されます。  
  
##  <a name="a-nameonidlea--cwinthreadonidle"></a><a name="onidle"></a>CWinThread::OnIdle  
 アイドル状態時の処理を実行するには、このメンバー関数をオーバーライドします。  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lCount`  
 カウンターは毎回増加`OnIdle`スレッドのメッセージ キューが空のときに呼び出されます。 この数は、新しいメッセージが処理されるたびに 0 にリセットされます。 使用することができます、`lCount`パラメーターをメッセージを処理することがなく、スレッドであったアイドル時間の相対的な長さを決定します。  
  
### <a name="return-value"></a>戻り値  
 さらにアイドル処理時間を受信する 0 以外の値これ以上アイドル状態の処理時間が必要な場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `OnIdle`スレッドのメッセージ キューが空とき、既定のメッセージ ループで呼び出されます。 これらに上書きを使用して、独自の背景にアイドル処理を呼び出します。  
  
 `OnIdle`アイドル処理に時間が必要ないことを示すために 0 を返すはずです。 `lCount`パラメーターはたびに増分`OnIdle`メッセージ キューが空で、新しいメッセージが処理されるたびに 0 にリセットされるときに呼び出されます。 この数に基づく、別のアイドル処理ルーチンを呼び出すことができます。  
  
 このメンバー関数の既定の実装では、一時オブジェクトとメモリから未使用のダイナミック リンク ライブラリを解放します。  
  
 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。  
  
 アプリケーションにまでメッセージを処理できないため`OnIdle`戻り値は、この関数で時間のかかるタスクを実行しません。  
  
##  <a name="a-nameoperatorhandlea--cwinthreadoperator-handle"></a><a name="operator_handle"></a>CWinThread::operator ハンドル  
 ハンドルを取得、`CWinThread`オブジェクトです。  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、スレッド オブジェクトのハンドルそれ以外の場合、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 ハンドルを使用して、Windows Api を直接呼び出します。  
  
##  <a name="a-namepostthreadmessagea--cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a>CWinThread::PostThreadMessage  
 別のユーザー定義メッセージを投稿すると呼ばれる`CWinThread`オブジェクトです。  
  
```  
BOOL PostThreadMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 ユーザー定義メッセージの ID。  
  
 `wParam`  
 最初のメッセージ パラメーター。  
  
 `lParam`  
 2 番目のメッセージのパラメーター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メッセージ マップ マクロで送信されたメッセージは、適切なメッセージ ハンドラーに割り当てられた`ON_THREAD_MESSAGE`します。  
  
> [!NOTE]
>  Windows を呼び出すときに[次](http://msdn.microsoft.com/library/windows/desktop/ms644946)MFC メッセージ ハンドラーが呼び出されない、MFC アプリケーション内で機能します。 詳細については、サポート技術情報の記事「prb:: MFC メッセージ ハンドラーいないと呼ばれるで PostThreadMessage()」(Q142415) を参照してください。  
  
##  <a name="a-namepretranslatemessagea--cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a>CWinThread::PreTranslateMessage  
 Windows 関数にディスパッチされる前に、ウィンドウ メッセージをフィルター処理するには、この関数をオーバーライド[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)します。  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 指す、 [MSG 構造体](../../mfc/reference/msg-structure1.md)処理するメッセージを格納しています。  
  
### <a name="return-value"></a>戻り値  
 メッセージを完全に処理された場合は&0; 以外`PreTranslateMessage`し、さらに処理する必要があります。 メッセージは、通常どおりに処理必要がある場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。  
  
##  <a name="a-nameprocessmessagefiltera--cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinThread::ProcessMessageFilter  
 フレームワークのフック関数は、フィルター処理し、特定の Windows メッセージに応答するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `code`  
 フック コードを指定します。 このメンバー関数では、コードを使用して、処理する方法を決定します。`lpMsg.`  
  
 `lpMsg`  
 Windows へのポインター [MSG 構造体](../../mfc/reference/msg-structure1.md)します。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フック関数の処理、アプリケーションの通常のメッセージに送信する前にイベントを処理します。  
  
 この高度な機能をオーバーライドする場合は、フレームワークを維持するために基本クラスのバージョンを呼び出すことを確認する処理をフックします。  
  
##  <a name="a-nameprocesswndprocexceptiona--cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinThread::ProcessWndProcException  
 フレームワークは、ハンドラーがスレッドのメッセージ、またはコマンド ハンドラーのいずれかでスローされる例外をキャッチしていないときに、このメンバー関数を呼び出します。  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *e*  
 未処理の例外へのポインター。  
  
 `pMsg`  
 指す、 [MSG 構造体](../../mfc/reference/msg-structure1.md)フレームワークが例外をスローする原因となった windows メッセージに関する情報を格納します。  
  
### <a name="return-value"></a>戻り値  
 – 1 の場合、`WM_CREATE`例外が生成されます。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を直接呼び出さないでください。  
  
 このメンバー関数の既定の実装では、次のメッセージから生成される例外のみを処理します。  
  
|コマンド|操作|  
|-------------|------------|  
|`WM_CREATE`|失敗します。|  
|`WM_PAINT`|検証対象のウィンドウ間を回避する`WM_PAINT`メッセージは生成されません。|  
  
 グローバルに、例外の処理を提供するには、この関数をオーバーライドします。 既定の動作を表示する場合にのみ、基本機能を呼び出します。  
  
 このメンバー関数は、メッセージ ポンプが含まれるスレッドでのみ使用されます。  
  
##  <a name="a-namepumpmessagea--cwinthreadpumpmessage"></a><a name="pumpmessage"></a>CWinThread::PumpMessage  
 スレッドのメッセージ ループが含まれています。  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>コメント  
 `PumpMessage`スレッドのメッセージ ループが含まれています。 **PumpMessage**によって呼び出される`CWinThread`スレッドのメッセージ ポンプにします。 呼び出すことができます`PumpMessage`を強制的に処理されるメッセージを上書きするか直接`PumpMessage`を既定の動作を変更します。  
  
 呼び出す`PumpMessage`直接および既定の動作をオーバーライドする上級ユーザーだけはお勧めします。  
  
##  <a name="a-nameresumethreada--cwinthreadresumethread"></a><a name="resumethread"></a>Cwinthread::resumethread  
 が中断されたスレッドの実行を再開すると呼ばれる、 [SuspendThread](#suspendthread)メンバー関数、またはで作成されたスレッド、 **CREATE_SUSPENDED**フラグ。  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>戻り値  
 スレッドの前のカウントが成功した場合の中断`0xFFFFFFFF`それ以外の場合。 戻り値が&0; の場合は、現在のスレッドが中断されません。 戻り値が&1; つの場合は、スレッドが中断されたですが再起動されます。 戻り値より大きい値を&1; つは、スレッドが中断しています。  
  
### <a name="remarks"></a>コメント  
 現在のスレッドの中断カウントは&1; つを減少します。 中断カウントが圧縮されて場合ゼロにスレッドが実行を再開それ以外の場合、スレッドが中断しています。  
  
##  <a name="a-nameruna--cwinthreadrun"></a><a name="run"></a>CWinThread::Run  
 ユーザー インターフェイス スレッドの既定のメッセージ ループを提供します。  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>戻り値  
 `int`スレッドによって返される値。 この値は、呼び出すことによって取得できる[GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)します。  
  
### <a name="remarks"></a>コメント  
 **実行**を取得し、アプリケーションが受信するまでに Windows メッセージをディスパッチ、 [WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641)メッセージです。 スレッドのメッセージ キューにメッセージがない場合**実行**呼び出し`OnIdle`アイドル時間の処理を実行します。 受信メッセージ、 [PreTranslateMessage](#pretranslatemessage)特別な処理され、次に、メンバー関数[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)標準キーボードの翻訳のためです。 最後に、 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数が呼び出されます。  
  
 **実行**オーバーライドされることはほとんどありませんが特別な動作を実装するメソッドをオーバーライドすることができます。  
  
 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。  
  
##  <a name="a-namesetthreadprioritya--cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a>CWinThread::SetThreadPriority  
 この関数は、その優先度クラス内の現在のスレッドの優先度レベルを設定します。  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPriority`  
 優先度クラス内で新しいスレッドの優先順位を指定します。 このパラメーターは、優先度の高い順に一覧表示、次の値のいずれかを指定する必要があります。  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 これらの優先順位の詳細については、次を参照してください。 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 後にのみ呼び出すことができます[CreateThread](#createthread)が正常に終了します。  
  
##  <a name="a-namesuspendthreada--cwinthreadsuspendthread"></a><a name="suspendthread"></a>CWinThread::SuspendThread  
 インクリメントの現在のスレッドの数を一時停止します。  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>戻り値  
 スレッドの前のカウントが成功した場合の中断`0xFFFFFFFF`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 任意のスレッドにゼロよりも中断カウントがある場合は、そのスレッドは実行されません。 呼び出してスレッドを再開できる、 [ResumeThread](#resumethread)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)

