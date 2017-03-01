---
title: "アプリケーションの情報と管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
caps.latest.revision: 17
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
ms.openlocfilehash: cc9adde202f211d6e0a536e949b42772f0890ef6
ms.lasthandoff: 02/24/2017

---
# <a name="application-information-and-management"></a>アプリケーションの情報と管理
アプリケーションを作成するときに、1 つを作成する[CWinApp](../../mfc/reference/cwinapp-class.md)-派生オブジェクト。 時々、外部からは、このオブジェクトに関する情報を取得することがあります、 `CWinApp`-派生オブジェクト。  
  
 Microsoft Foundation Class ライブラリは、これらのタスクを達成するために、次のグローバル関数を提供します。  
  
### <a name="application-information-and-management-functions"></a>アプリケーションの情報と管理機能  
  
|||  
|-|-|  
|[AfxBeginThread](#afxbeginthread)|新しいスレッドを作成します。|  
|[AfxEndThread](#afxendthread)|現在のスレッドを終了します。|  
|[AfxFreeLibrary](#afxfreelibrary)|読み込まれたダイナミック リンク ライブラリ (DLL) モジュールの参照カウントをデクリメント参照カウントが&0; になったときに、このモジュールはマップされています。|  
|[AfxGetApp](#afxgetapp)|アプリケーションへのポインターの&1; つを返します`CWinApp`オブジェクトです。|  
|[AfxGetAppName](#afxgetappname)|アプリケーションの名前を含む文字列を返します。|  
|[AfxGetInstanceHandle](#afxgetinstancehandle)|返します。、`HINSTANCE`アプリケーションのこのインスタンスを表します。|  
|[AfxGetMainWnd](#afxgetmainwnd)|非 OLE アプリケーションの現在の"main"ウィンドウまたはサーバー アプリケーションの埋め込み先フレーム ウィンドウへのポインターを返します。|  
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|この関数を使用して、アプリケーションがレジストリ アクセスをリダイレクトするかどうかを判断、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。|  
|[AfxGetResourceHandle](#afxgetresourcehandle)|返します。、`HINSTANCE`アプリケーションの既定のリソースのソースにします。 アプリケーションのリソースに直接アクセスするのにには、これを使用します。|  
|[AfxGetThread](#afxgetthread)|現在のポインターを取得[CWinThread](../../mfc/reference/cwinthread-class.md)オブジェクトです。|  
|[AfxInitRichEdit](#afxinitrichedit)|1.0 リッチ エディット コントロール、アプリケーションのバージョンを初期化します。|  
|[AfxInitRichEdit2](#afxinitrichedit2)|2.0 以降のリッチ エディット コントロール、アプリケーションのバージョンを初期化します。|  
|[AfxLoadLibrary](#afxloadlibrary)|DLL モジュールをマップし、DLL 関数のアドレスを取得するために使用できるハンドルを返します。|  
|[AfxRegisterClass](#afxregisterclass)|MFC を使用する DLL には、ウィンドウ クラスを登録します。|  
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC によって自動的に登録したを補足するために Windows のウィンドウ クラスを登録します。|  
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|アプリケーションがレジストリ アクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。|  
|[AfxSetResourceHandle](#afxsetresourcehandle)|セット、`HINSTANCE`ハンドルは、アプリケーションの既定のリソースが読み込まれます。|  
|[AfxSocketInit](#afxsocketinit)|呼び出される、 `CWinApp::InitInstance` Windows Sockets を初期化するためにオーバーライドします。|  
|[AfxWinInit](#afxwininit)|MFC が指定したによって呼び出されます`WinMain`の一部としての関数、 [CWinApp](../../mfc/reference/cwinapp-class.md)の GUI ベースのアプリケーションで MFC を初期化するために初期化します。 MFC を使用するコンソール アプリケーションを直接呼び出す必要があります。|  
  

  
##  <a name="a-nameafxbeginthreada--afxbeginthread"></a><a name="afxbeginthread"></a>AfxBeginThread  
 この関数を呼び出して、新しいスレッドを作成します。  
  
```   
CWinThread* AfxBeginThread(
    AFX_THREADPROC pfnThreadProc,  
    LPVOID pParam,  
    int nPriority = THREAD_PRIORITY_NORMAL,  
    UINT nStackSize = 0,  
    DWORD dwCreateFlags = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);

CWinThread* AfxBeginThread(
    CRuntimeClass* pThreadClass,  
    int nPriority = THREAD_PRIORITY_NORMAL,  
    UINT nStackSize = 0,  
    DWORD dwCreateFlags = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pfnThreadProc`  
 ワーカー スレッドの制御関数をポイントします。 ことはできません**NULL**します。 この関数は次のように宣言する必要があります。  
  
 `UINT __cdecl MyControllingFunction( LPVOID pParam );`  
  
 *pThreadClass*  
 派生したオブジェクトの対象となる[CWinThread](../../mfc/reference/cwinthread-class.md)します。  
  
 *pParam*  
 `pfnThreadProc` の関数の宣言へのパラメーターに示されるように、制御関数に渡すパラメーター。  
  
 `nPriority`  
 スレッドの優先順位。 完全な一覧と使用可能な優先事項の説明では、「 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `nStackSize`  
 新しいスレッドへのスタックのバイト サイズを指定します。 0 である場合、スタック サイズの既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。  
  
 `dwCreateFlags`  
 スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の&1; つを含めることができます。  
  
- **CREATE_SUSPENDED**中断カウントを&1; としてスレッドを開始します。 使用**CREATE_SUSPENDED**のメンバー データを初期化する場合、`CWinThread`などのオブジェクト[m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete)またはスレッドが実行を開始する前に、派生クラスのメンバーです。 初期化が完了した後を使用して[cwinthread::resumethread](../../mfc/reference/cwinthread-class.md#resumethread)を実行しているスレッドを開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。  
  
- **0**作成後すぐにスレッドを開始します。  
  
 `lpSecurityAttrs`  
 指す、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)をスレッドのセキュリティ属性を指定します。 場合**NULL**、使用されるスレッドの作成と同じセキュリティ属性します。 この構造体の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたスレッド オブジェクトへのポインターまたは**NULL**障害が発生した場合。  
  
### <a name="remarks"></a>コメント  
 `AfxBeginThread` の最初のフォームはワーカー スレッドを作成します。 2 番目のフォームは、ユーザー インターフェイス スレッドまたはワーカー スレッドとして機能可能なスレッドを作成します。  
  
 `AfxBeginThread`新たに作成`CWinThread`オブジェクトを呼び出してその[CreateThread](../../mfc/reference/cwinthread-class.md#createthread)スレッドの実行を開始する機能、スレッドへのポインターを返します。 なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。 スレッドを終了する[AfxEndThread](#afxendthread)からスレッドまたはワーカー スレッドの制御関数からの戻り値に含まれています。  
  
 マルチスレッドは、アプリケーションによって有効化される必要があります。それ以外の場合、この関数は失敗します。 マルチ スレッド処理を有効にする方法の詳細についてを参照してください[/MD、/MT、/LD (ランタイム ライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md)  *Visual C コンパイラ オプション*します。  
  
 詳細については`AfxBeginThread`、記事を参照して[マルチ スレッド: ワーカー スレッドの作成](../../parallel/multithreading-creating-worker-threads.md)と[マルチ スレッド: ユーザー インターフェイス スレッドの作成](../../parallel/multithreading-creating-user-interface-threads.md)します。  
  
### <a name="example"></a>例  
 例を参照してください[csocket::attach](../../mfc/reference/csocket-class.md#attach)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxendthreada--afxendthread"></a><a name="afxendthread"></a>AfxEndThread  
 この関数では、現在実行中のスレッドを終了します。  
  
```   
void AFXAPI AfxEndThread(
    UINT nExitCode,  
    BOOL bDelete  = TRUE); 
```  
  
### <a name="parameters"></a>パラメーター  
 *nExitCode*  
 スレッドの終了コードを指定します。  
  
 *bDelete*  
 メモリからスレッド オブジェクトを削除します。  
  
### <a name="remarks"></a>コメント  
 終了するスレッド内からを呼び出す必要があります。  
  
 詳細については`AfxEndThread`、記事を参照して[マルチ スレッド: スレッドの終了](../../parallel/multithreading-terminating-threads.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxfreelibrarya--afxfreelibrary"></a><a name="afxfreelibrary"></a>AfxFreeLibrary  
 両方とも`AfxFreeLibrary`と`AfxLoadLibrary`ライブラリが読み込まれたモジュールごとに参照カウントを保持します。  
  
```   
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib); 
```  
  
### <a name="parameters"></a>パラメーター  
 *hInstLib*  
 読み込まれたライブラリ モジュールのハンドル。 [AfxLoadLibrary](#afxloadlibrary)このハンドルを返します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE** 、関数が成功した場合は、それ以外の場合、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 `AfxFreeLibrary`読み込まれたダイナミック リンク ライブラリ (DLL) モジュールの参照カウントをデクリメントします。 参照カウントが&0; になったし、モジュールが呼び出し元プロセスのアドレス空間から割り当てられたハンドルは無効になります。 この参照カウントは毎回`AfxLoadLibrary`が呼び出されます。  
  
 ライブラリ モジュールを解放する前に、システムは、それを使用して、プロセスからデタッチする DLL を使用できます。 これが、DLL、現在のプロセスに割り当てられているリソースをクリーンアップできます。 エントリ ポイント関数が返されると、ライブラリ モジュールは、現在のプロセスのアドレス空間から削除されます。  
  
 使用`AfxLoadLibrary`DLL モジュールにマップします。  
  
 使用してください`AfxFreeLibrary`と`AfxLoadLibrary`(Win32 関数ではなく**FreeLibrary**と**LoadLibrary**) 場合は、アプリケーションが複数のスレッドを使用します。 使用して`AfxLoadLibrary`と`AfxFreeLibrary`スタートアップおよびシャット ダウン コード DLL の読み込みし、アンロードの拡張機能が MFC のグローバル状態を破損していないときに実行されることを確認します。  
  
### <a name="example"></a>例  
 例を参照してください[AfxLoadLibrary](#afxloadlibrary)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdll_.h  
  
##  <a name="a-nameafxgetappa--afxgetapp"></a><a name="afxgetapp"></a>AfxGetApp  
 この関数によって返されるポインターを使用して、メッセージのディスパッチのメイン コードや最上位ウィンドウなどのアプリケーションの情報にアクセスすることができます。  
  
```   
CWinApp* AFXAPI AfxGetApp(); 
```  
  
### <a name="return-value"></a>戻り値  
 1 つへのポインター`CWinApp`アプリケーションのオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、NULL を返す場合を示しているアプリケーション €™ s のメイン ウィンドウが完全にまだ初期化されていません。 これは、も発生している可能性があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&126;](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxgetappnamea--afxgetappname"></a><a name="afxgetappname"></a>AfxGetAppName  
 この関数によって返される文字列は、一時的な文字列名診断メッセージ、またはルートとして使用できます。  
  
```   
LPCTSTR AFXAPI AfxGetAppName(); 
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションの名前を表す null で終わる文字列。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#127;](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxgetinstancehandlea--afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a>AfxGetInstanceHandle  
 この関数では、現在のアプリケーションのインスタンス ハンドルを取得することができます。  
  
```   
HINSTANCE  AFXAPI AfxGetInstanceHandle(); 
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`アプリケーションの現在のインスタンスにします。 MFC の USRDLL バージョンとリンクする DLL 内から呼び出された場合、 `HINSTANCE` DLL が返されます。  
  
### <a name="remarks"></a>コメント  
 `AfxGetInstanceHandle`常に返します、`HINSTANCE`実行可能ファイルの (します。EXE) DLL が MFC の USRDLL バージョンとリンク内から呼び出された場合を除き、します。 この場合、それを返します、 `HINSTANCE` DLL にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&128;](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxgetmainwnda--afxgetmainwnd"></a><a name="afxgetmainwnd"></a>AfxGetMainWnd  
 アプリケーションが OLE サーバーである場合は、直接参照することではなくアプリケーションのアクティブなメイン ウィンドウへのポインターを取得するには、この関数を呼び出して、 [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd)アプリケーション オブジェクトのメンバーです。  
  
```   
CWnd* AFXAPI AfxGetMainWnd(); 
```  
  
### <a name="return-value"></a>戻り値  
 サーバーが、コンテナー内に埋め込まれているアクティブなオブジェクトを持ち、そのコンテナーがアクティブである場合は、この関数は、埋め込まれているアクティブな文書を含むフレーム ウィンドウ オブジェクトへのポインターを返します。  
  
 コンテナー内に埋め込まれているアクティブなオブジェクトが存在しない場合や、開発中のアプリケーションが OLE サーバーではない場合は、この関数は単純に、開発中のアプリケーション オブジェクトの `m_pMainWnd` を返します。  
  
 `AfxGetMainWnd` をアプリケーションのプライマリ スレッドから呼び出した場合は、上記の規則に従ってアプリケーションのメイン ウィンドウを返します。 アプリケーションのセカンダリ スレッドからこの関数を呼び出した場合は、関数は呼び出しを行ったスレッドに関連付けられているメイン ウィンドウを返します。  
  
### <a name="remarks"></a>コメント  
 開発中のアプリケーションが OLE サーバーではない場合は、この関数を呼び出すことは、アプリケーション オブジェクトの `m_pMainWnd` メンバーを直接参照することと同じです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&129;](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxgetperuserregistrationa--afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a>AfxGetPerUserRegistration  
 この関数を使用して、アプリケーションがレジストリ アクセスをリダイレクトするかどうかを判断、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。  
  
```  
BOOL AFXAPI AfxGetPerUserRegistration();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`レジストリ情報が転送されるかを示す、 **HKCU**ノードです。`FALSE`アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードが**HKEY_CLASSES_ROOT** ( **HKCR**)。  
  
### <a name="remarks"></a>コメント  
 レジストリのリダイレクトを有効にした場合、framework からのアクセスにリダイレクト**HKCR**に**する**です。 MFC と ATL のフレームワークは、リダイレクトの影響を受けます。  
  
 アプリケーションがレジストリ アクセスをリダイレクトするかどうかを変更するには、使用[AfxSetPerUserRegistration](#afxsetperuserregistration)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxstat_.h    
  
##  <a name="a-nameafxgetresourcehandlea--afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a>AfxGetResourceHandle  
 使用して、`HINSTANCE`アプリケーションのリソースに直接アクセスする、たとえば、Windows の関数の呼び出しでは、この関数によって返されたハンドル**FindResource**します。  
  
```   
extern HINSTANCE  AfxGetResourceHandle(); 
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`ハンドルは、アプリケーションの既定のリソースが読み込まれます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&130;](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxgetthreada--afxgetthread"></a><a name="afxgetthread"></a>AfxGetThread  
 ポインターを取得するには、この関数を呼び出して、 [CWinThread](../../mfc/reference/cwinthread-class.md)実行中のスレッドを表すオブジェクト。  
  
```   
CWinThread* AfxGetThread(); 
```  
  
### <a name="return-value"></a>戻り値  
 実行中のスレッドへのポインターそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 目的のスレッド内からを呼び出す必要があります。  
  
> [!NOTE]
>  MFC プロジェクト通話を移植する場合`AfxGetThread`Visual C version 4.2、5.0 または 6.0 から`AfxGetThread`呼び出し[AfxGetApp](#afxgetapp)スレッドが存在しない場合。 Visual C+ .NET 以降では、`AfxGetThread`返します**NULL**スレッドが検出されなかった場合。 アプリケーションのスレッドを実行する場合に、呼び出す必要があります`AfxGetApp`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&132;](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxinitrichedita--afxinitrichedit"></a><a name="afxinitrichedit"></a>AfxInitRichEdit  
 この関数では、アプリケーションのリッチ エディット コントロール (version 1.0) を初期化します。  
  
```   
BOOL AFXAPI AfxInitRichEdit(); 
```  
  
### <a name="remarks"></a>コメント  
 この関数は、旧バージョンと互換性のために提供されます。 Visual C .NET および後で使用するで作成されたアプリケーション[AfxInitRichEdit2](#afxinitrichedit2)します。  
  
 `AfxInitRichEdit`RICHED32 を読み込みます。リッチ エディット コントロールのバージョン 1.0 を初期化するために DLL です。 2.0 および 3.0 RICHED20、リッチ エディット コントロールのバージョンを使用します。DLL を読み込む必要があります。 呼び出しにこれは[AfxInitRichEdit2](#afxinitrichedit2)します。 ダイアログ リソースが存在するには、Visual C .NET の前に作成されたリッチ エディット コントロールで、リッチ エディット コントロール、自動的にバージョン 1.0 です。 リッチ エディット コントロールで Visual C .NET リソース エディターを使用して挿入は、バージョン 2.0 です。  
  
 既存の Visual C アプリケーションをバージョン 2.0 でリッチ エディット コントロールを更新するには、開く、します。RC ファイルのテキストでは、"RichEdit20a"を"RICHEDIT"から各リッチ エディット コントロールのクラス名を変更します。 呼び出しを置き換える`AfxInitRichEdit`と`AfxInitRichEdit2`です。  
  
 この関数は、ライブラリに、プロセスの初期化されていない場合も、共通のコントロール ライブラリを初期化します。 リッチ エディット コントロールを MFC アプリケーションから直接使用する場合は、MFC でリッチ エディット コントロールのランタイムが正しく開始されたことを保証するためには、この関数を呼び出す必要があります。 Create メソッドを呼び出す場合[CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)、通常がなくてもこの関数を呼び出すが、場合によっては必要な場合があります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxinitrichedit2a--afxinitrichedit2"></a><a name="afxinitrichedit2"></a>AfxInitRichEdit2  
 この関数では、アプリケーションのリッチ エディット コントロール (バージョン 2.0 以降) を初期化します。  
  
```   
BOOL AFXAPI AfxInitRichEdit2(); 
```  
  
### <a name="remarks"></a>コメント  
 この関数では、RICHED20 をロードします。DLL と初期化、多機能のバージョン 2.0 は、コントロールを編集します。 Create メソッドを呼び出す場合[CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)、通常がなくてもこの関数を呼び出すが、場合によっては必要な場合があります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxloadlibrarya--afxloadlibrary"></a><a name="afxloadlibrary"></a>AfxLoadLibrary  
 使用`AfxLoadLibrary`DLL モジュールにマップします。  
  
```   
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName); 
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszModuleName*  
 モジュールの名前を含む null で終わる文字列へのポインター (どちらか、です。DLL またはです。実行可能ファイルの場合)。 指定した名前は、モジュールのファイル名です。  
  
 文字列のパスを指定するファイルが、指定したディレクトリに存在しない場合は、この関数は失敗します。  
  
 パスが指定されていないと、ファイル名拡張子を省略すると、既定の拡張機能です。DLL が追加されます。 ただし、ファイル名文字列には、ピリオド文字 (.)、モジュール名に拡張機能がないことを表しますを含めることができます。 パスが指定されていない場合、関数は、次の順序でファイルを検索します。  
  
-   アプリケーションの読み込み元となるディレクトリ。  
  
-   現在のフォルダー。  
  
- **Windows 95/98:** Windows システム ディレクトリ。 **Windows NT:** 32 ビット Windows システム ディレクトリ。 このディレクトリの名前は、SYSTEM32 です。  
  
- **Windows NT のみ:** 16 ビットの Windows システム ディレクトリ。 このディレクトリのパスを取得する Win32 関数はありませんを検索します。 このディレクトリの名前は、システムです。  
  
-   Windows ディレクトリ。  
  
-   PATH 環境変数で指定されているディレクトリです。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、モジュールへのハンドルを返します。 関数が失敗した場合、戻り値は NULL です。  
  
### <a name="remarks"></a>コメント  
 使用できるハンドルを返す[GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) DLL 関数のアドレスを取得します。 `AfxLoadLibrary`その他の実行可能モジュールにマップするにも使用できます。  
  
 各プロセスは、各ライブラリが読み込まれたモジュールの参照カウントを維持できます。 この参照カウントは毎回`AfxLoadLibrary`と呼びます。 たび`AfxFreeLibrary`が呼び出されます。 参照カウントが&0; になったし、モジュールが呼び出し元プロセスのアドレス空間から割り当てられたハンドルは無効になります。  
  
 使用してください`AfxLoadLibrary`と`AfxFreeLibrary`(Win32 関数ではなく**LoadLibrary**と**FreeLibrary**) 拡張 DLL を動的に読み込む場合と、アプリケーションは、複数のスレッドを使用している場合。 使用して`AfxLoadLibrary`と`AfxFreeLibrary`拡張 DLL が読み込まれ、アンロードされたときに実行されるスタートアップおよびシャット ダウン コードが MFC のグローバル状態が破損しないことを保証します。  
  
 使用して`AfxLoadLibrary`アプリケーションでは MFC の DLL バージョンに動的にリンクすることが必要です。 用のヘッダー ファイル`AfxLoadLibrary`、Afxdll_.h、は、MFC が DLL としてのアプリケーションにリンクされている場合に含まれます。 これは仕様を使用または拡張 Dll を作成する MFC の DLL バージョンにリンクする必要があるためです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_DLLUser&#1;](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]  
[!code-cpp[NVC_MFC_DLLUser&#2;](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]  
[!code-cpp[NVC_MFC_DLLUser&#3;](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdll_.h  
   
  
##  <a name="a-nameafxregisterclassa--afxregisterclass"></a><a name="afxregisterclass"></a>AfxRegisterClass  
 この関数を使用すると、MFC を使用する DLL でウィンドウ クラスを登録できます。  
  
```   
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass); 
```  
  
### <a name="parameters"></a>パラメーター  
 *lpWndClass*  
 ポインター、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造が登録されるウィンドウ クラスに関する情報を格納します。 この構造体の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**クラスが正常に登録されている、それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用する場合、クラスは、自動的に登録された DLL がアンロードされるときです。  
  
 非 DLL のビルドでは、`AfxRegisterClass`識別子が Windows 関数にマップするマクロとして定義されている**RegisterClass**であるため、アプリケーションに登録されたクラスは自動的に登録します。 使用する場合`AfxRegisterClass`の代わりに**RegisterClass**アプリケーションと DLL の両方を変更せずに、コードを使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_DLL&3;](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxregisterwndclassa--afxregisterwndclass"></a><a name="afxregisterwndclass"></a>AfxRegisterWndClass  
 独自のウィンドウ クラスを登録できます。  
  
```  
 
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,  
    HCURSOR hCursor = 0,  
    HBRUSH hbrBackground = 0,  
    HICON hIcon = 0);  
```  
  
### <a name="parameters"></a>パラメーター  
 *nClassStyle*  
 Windows クラスのスタイル、またはビットごとの OR を使用して作成されたスタイルの組み合わせを指定します ( **|**) ウィンドウ クラスの演算子です。 クラスのスタイルの一覧は、次を参照してください。、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 場合**NULL**、既定値は次のように設定されます。  
  
-   マウスのスタイルを設定**CS_DBLCLKS**を送信し、ユーザーがマウスをダブルクリックすると、ウィンドウ プロシージャへのメッセージ をダブルクリックします。  
  
-   Windows 標準への矢印カーソル スタイル設定**IDC_ARROW**します。  
  
-   背景ブラシが設定**NULL**ので、ウィンドウは、背景を消去できません。  
  
-   アイコンを手を振るフラグの標準の Windows ロゴ アイコンに設定します。  
  
 `hCursor`  
 ウィンドウ クラスから作成された各ウィンドウにインストールする、カーソルのリソースへのハンドルを指定します。 既定値を使用する場合**0**、標準がくる**IDC_ARROW**カーソル。  
  
 *hbrBackground*  
 ウィンドウ クラスから作成された各ウィンドウにインストールするブラシ リソースを識別するハンドルを指定します。 既定値を使用する場合**0**、必要があります、 **NULL**背景のブラシと、ウィンドウには、既定では、そのバック グラウンド処理中には消去されません[WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)します。  
  
 `hIcon`  
 ウィンドウ クラスから作成された各ウィンドウにインストールする、アイコン リソースを識別するハンドルを指定します。 既定値を使用する場合**0**、標準、手を振るフラグの Windows ロゴ アイコンが表示されます。  
  
### <a name="return-value"></a>戻り値  
 クラス名を含む null で終わる文字列。 このクラス名を渡すことができます、**作成**のメンバー関数内`CWnd`またはその他の**CWnd-**ウィンドウを作成するクラスを派生します。 名前は、Microsoft Foundation Class ライブラリによって生成されます。  
  
> [!NOTE]
>  戻り値は、静的バッファーへのポインターです。 この文字列を保存するには、それを割り当てる、`CString`変数です。  
  
### <a name="remarks"></a>コメント  
 Microsoft Foundation Class ライブラリでは、いくつかの標準のウィンドウ クラスが自動的に登録します。 独自のウィンドウ クラスを登録する場合は、この関数を呼び出します。  
  
 クラスの名前が登録されている`AfxRegisterWndClass`パラメーターにのみ依存します。 呼び出した場合`AfxRegisterWndClass`複数回同一のパラメーターを使用してのみクラスを登録する最初の呼び出しです。 後続の呼び出しに対して`AfxRegisterWndClass`と同じパラメーターを使用して既に登録されているクラス名を返すだけです。  
  
 呼び出した場合`AfxRegisterWndClass`クラスごとに別のウィンドウ クラスを取得する代わりに、同じパラメーターを使用して複数の CWnd から派生したクラスの各クラスは、同じウィンドウ クラスを共有します。 問題が発生する場合はこれ、 **CS_CLASSDC**クラスのスタイルを使用します。 複数のではなく**CS_CLASSDC** 、ウィンドウ クラス、最終的には&1; つ**CS_CLASSDC**ウィンドウ クラス、およびクラスが同じドメイン コント ローラーを共有することを使用するすべての C++ windows です。 この問題を避けるためには、呼び出す[AfxRegisterClass](#afxregisterclass)クラスを登録します。  
  
 テクニカル ノートを参照してください[TN001: ウィンドウ クラスの登録](../../mfc/tn001-window-class-registration.md)ウィンドウ クラスの登録の詳細については、`AfxRegisterWndClass`関数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&134;](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxsetperuserregistrationa--afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a>AfxSetPerUserRegistration  
 アプリケーションがレジストリ アクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。  
  
```  
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`レジストリ情報が転送されるかを示す、 **HKCU**ノードです。`FALSE`アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードが**HKEY_CLASSES_ROOT** ( **HKCR**)。  
  
### <a name="remarks"></a>コメント  
 前に[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]、通常、レジストリにアクセスするアプリケーションを使用して、 **HKEY_CLASSES_ROOT**ノードです。 ただし、[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]への書き込みに管理者特権モードでアプリケーションを実行する必要があります**HKCR**します。  
  
 このメソッドにより、アプリケーションからレジストリへのアクセスをリダイレクトすることで、管理者特権モードで実行せずに、レジストリに読み書きを**HKCR**に**HKCU**します。 詳細については、次を参照してください。[リンカー プロパティ ページ](../../ide/linker-property-pages.md)します。  
  
 レジストリのリダイレクトを有効にした場合、framework からのアクセスにリダイレクト**HKCR**に**する**です。 MFC と ATL のフレームワークは、リダイレクトの影響を受けます。  
  
 既定の実装の下のレジストリにアクセスする**HKCR**します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxstat_.h    
  
##  <a name="a-nameafxsetresourcehandlea--afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a>AfxSetResourceHandle  
 この関数を使って設定、`HINSTANCE`アプリケーションの既定のリソースが読み込まれる場所を指定のハンドル。  
  
```  
 
void  
AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstResource`  
 インスタンスまたはモジュールを識別するハンドルをします。アプリケーションのリソースの読み込み元となる EXE または DLL ファイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&135;](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxsocketinita--afxsocketinit"></a><a name="afxsocketinit"></a>AfxSocketInit  
 この関数を呼び出して、 `CWinApp::InitInstance` Windows Sockets を初期化するためにオーバーライドします。  
  
```  
 
BOOL  
AfxSocketInit(WSADATA* lpwsaData = NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpwsaData`  
 ポインター、 [WSADATA](../../mfc/reference/wsadata-structure.md)構造体。 場合`lpwsaData`と等しくない`NULL`のアドレス、`WSADATA`構造がへの呼び出しで埋められた`WSAStartup`します。 この関数も確実に`WSACleanup`は、アプリケーションが終了する前にするの呼び出されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 静的にリンクされた MFC アプリケーションのセカンダリ スレッドで MFC ソケットを使用する場合を呼び出す必要があります`AfxSocketInit`ソケット ライブラリを初期化するソケットを使用する各スレッドにします。 既定では、`AfxSocketInit`はプライマリ スレッドでのみ呼び出されます。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxsock.h  
  
##  <a name="a-nameafxwininita--afxwininit"></a><a name="afxwininit"></a>AfxWinInit  
 この関数は MFC 提供によって呼び出されます`WinMain`の一部としての関数、 [CWinApp](../../mfc/reference/cwinapp-class.md)の GUI ベースのアプリケーションで MFC を初期化するために初期化します。  
  
```  
 
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,  
    HINSTANCE hPrevInstance,  
    LPTSTR lpCmdLine,  
    int nCmdShow);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 現在実行中のモジュールのハンドル。  
  
 *hPrevInstance*  
 アプリケーションの以前のインスタンスへのハンドル。 Win32 ベースのアプリケーションでは、このパラメーターは常に**NULL**します。  
  
 `lpCmdLine`  
 アプリケーションのコマンドラインを指定する null で終わる文字列へのポインター。  
  
 `nCmdShow`  
 GUI アプリケーションのメイン ウィンドウの表示方法を指定します。  
  
### <a name="remarks"></a>コメント  
 コンソール アプリケーションでは、これを使用しません MFC によって付与される`WinMain`関数を呼び出す必要があります`AfxWinInit`mfc します。  
  
 呼び出した場合`AfxWinInit`のインスタンスを宣言、自分で、`CWinApp`クラスです。 コンソール アプリケーションにすることもできましていない独自のクラスから派生`CWinApp`のインスタンスを代わりに使用して`CWinApp`直接します。 この手法は、アプリケーションのすべての機能の実装のままにする場合に適切な**メイン**します。  
  
> [!NOTE]
>  アセンブリのアクティベーション コンテキストを作成するとき、MFC は、ユーザーのモジュールで提供されるマニフェストのリソースを使用します。 アクティブ化コンテキストは`AfxWinInit`です。 詳細については、次を参照してください。[の MFC モジュール状態でアクティブ化コンテキストのサポート](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_AfxWinInit&#1;](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]  

### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)

