---
title: "CHtmlView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlView
- AFXHTML/CHtmlView
- AFXHTML/CHtmlView::Create
- AFXHTML/CHtmlView::CreateControlSite
- AFXHTML/CHtmlView::ExecFormsCommand
- AFXHTML/CHtmlView::ExecWB
- AFXHTML/CHtmlView::GetAddressBar
- AFXHTML/CHtmlView::GetApplication
- AFXHTML/CHtmlView::GetBusy
- AFXHTML/CHtmlView::GetContainer
- AFXHTML/CHtmlView::GetFullName
- AFXHTML/CHtmlView::GetFullScreen
- AFXHTML/CHtmlView::GetHeight
- AFXHTML/CHtmlView::GetHtmlDocument
- AFXHTML/CHtmlView::GetLeft
- AFXHTML/CHtmlView::GetLocationName
- AFXHTML/CHtmlView::GetLocationURL
- AFXHTML/CHtmlView::GetMenuBar
- AFXHTML/CHtmlView::GetOffline
- AFXHTML/CHtmlView::GetParentBrowser
- AFXHTML/CHtmlView::GetProperty
- AFXHTML/CHtmlView::GetReadyState
- AFXHTML/CHtmlView::GetRegisterAsBrowser
- AFXHTML/CHtmlView::GetRegisterAsDropTarget
- AFXHTML/CHtmlView::GetSilent
- AFXHTML/CHtmlView::GetSource
- AFXHTML/CHtmlView::GetStatusBar
- AFXHTML/CHtmlView::GetTheaterMode
- AFXHTML/CHtmlView::GetToolBar
- AFXHTML/CHtmlView::GetTop
- AFXHTML/CHtmlView::GetTopLevelContainer
- AFXHTML/CHtmlView::GetType
- AFXHTML/CHtmlView::GetVisible
- AFXHTML/CHtmlView::GetWidth
- AFXHTML/CHtmlView::GoBack
- AFXHTML/CHtmlView::GoForward
- AFXHTML/CHtmlView::GoHome
- AFXHTML/CHtmlView::GoSearch
- AFXHTML/CHtmlView::LoadFromResource
- AFXHTML/CHtmlView::Navigate
- AFXHTML/CHtmlView::Navigate2
- AFXHTML/CHtmlView::OnBeforeNavigate2
- AFXHTML/CHtmlView::OnCommandStateChange
- AFXHTML/CHtmlView::OnDocumentComplete
- AFXHTML/CHtmlView::OnDocWindowActivate
- AFXHTML/CHtmlView::OnDownloadBegin
- AFXHTML/CHtmlView::OnDownloadComplete
- AFXHTML/CHtmlView::OnEnableModeless
- AFXHTML/CHtmlView::OnFilterDataObject
- AFXHTML/CHtmlView::OnFrameWindowActivate
- AFXHTML/CHtmlView::OnFullScreen
- AFXHTML/CHtmlView::OnGetDropTarget
- AFXHTML/CHtmlView::OnGetExternal
- AFXHTML/CHtmlView::OnGetHostInfo
- AFXHTML/CHtmlView::OnGetOptionKeyPath
- AFXHTML/CHtmlView::OnHideUI
- AFXHTML/CHtmlView::OnMenuBar
- AFXHTML/CHtmlView::OnNavigateComplete2
- AFXHTML/CHtmlView::OnNavigateError
- AFXHTML/CHtmlView::OnNewWindow2
- AFXHTML/CHtmlView::OnProgressChange
- AFXHTML/CHtmlView::OnPropertyChange
- AFXHTML/CHtmlView::OnQuit
- AFXHTML/CHtmlView::OnResizeBorder
- AFXHTML/CHtmlView::OnShowContextMenu
- AFXHTML/CHtmlView::OnShowUI
- AFXHTML/CHtmlView::OnStatusBar
- AFXHTML/CHtmlView::OnStatusTextChange
- AFXHTML/CHtmlView::OnTheaterMode
- AFXHTML/CHtmlView::OnTitleChange
- AFXHTML/CHtmlView::OnToolBar
- AFXHTML/CHtmlView::OnTranslateAccelerator
- AFXHTML/CHtmlView::OnTranslateUrl
- AFXHTML/CHtmlView::OnUpdateUI
- AFXHTML/CHtmlView::OnVisible
- AFXHTML/CHtmlView::PutProperty
- AFXHTML/CHtmlView::QueryFormsCommand
- AFXHTML/CHtmlView::QueryStatusWB
- AFXHTML/CHtmlView::Refresh
- AFXHTML/CHtmlView::Refresh2
- AFXHTML/CHtmlView::SetAddressBar
- AFXHTML/CHtmlView::SetFullScreen
- AFXHTML/CHtmlView::SetHeight
- AFXHTML/CHtmlView::SetLeft
- AFXHTML/CHtmlView::SetMenuBar
- AFXHTML/CHtmlView::SetOffline
- AFXHTML/CHtmlView::SetRegisterAsBrowser
- AFXHTML/CHtmlView::SetRegisterAsDropTarget
- AFXHTML/CHtmlView::SetSilent
- AFXHTML/CHtmlView::SetStatusBar
- AFXHTML/CHtmlView::SetTheaterMode
- AFXHTML/CHtmlView::SetToolBar
- AFXHTML/CHtmlView::SetTop
- AFXHTML/CHtmlView::SetVisible
- AFXHTML/CHtmlView::SetWidth
- AFXHTML/CHtmlView::Stop
dev_langs:
- C++
helpviewer_keywords:
- browsers, MFC support for
- CHtmlView class
- WebBrowser control
- WebBrowser control, MFC support
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d9d96ab02a0c49a2ece12c933f5d550a46204a39
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="chtmlview-class"></a>CHtmlView クラス
MFC のドキュメント/ビュー アーキテクチャのコンテキストで WebBrowser コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CHtmlView : public CFormView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHtmlView::Create](#create)|WebBrowser コントロールを作成します。|  
|[CHtmlView::CreateControlSite](#createcontrolsite)|フォーム上のコントロールをホストするコントロール サイトのインスタンスを作成するために使用する、オーバーライド可能なメソッド。|  
|[CHtmlView::ExecFormsCommand](#execformscommand)|指定されたコマンドを `IOleCommandTarget::Exec` メソッドを使用して実行します。|  
|[CHtmlView::ExecWB](#execwb)|コマンドを実行します。|  
|[CHtmlView::GetAddressBar](#getaddressbar)|Internet Explorer オブジェクトのアドレス バーが表示されるかどうかを判別します。 (WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。)|  
|[CHtmlView::GetApplication](#getapplication)|Internet Explorer アプリケーションの現在のインスタンスを含むアプリケーションを表すアプリケーション オブジェクトを取得します。|  
|[CHtmlView::GetBusy](#getbusy)|ダウンロードやその他のアクティビティが進行中かどうかを示す値を取得します。|  
|[CHtmlView::GetContainer](#getcontainer)|WebBrowser コントロールのコンテナーを取得します。|  
|[CHtmlView::GetFullName](#getfullname)|Web ブラウザーに表示されるリソースのフル ネームを、パスも含めて取得します。 (WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。)|  
|[CHtmlView::GetFullScreen](#getfullscreen)|WebBrowser コントロールが全画面表示モードと標準ウィンドウ モードのどちらで動作しているかを示します。|  
|[CHtmlView::GetHeight](#getheight)|Internet Explorer のメイン ウィンドウの高さを取得します。|  
|[CHtmlView::GetHtmlDocument](#gethtmldocument)|アクティブな HTML ドキュメントを取得します。|  
|[CHtmlView::GetLeft](#getleft)|Internet Explorer のメイン ウィンドウの左端の画面座標を取得します。|  
|[CHtmlView::GetLocationName](#getlocationname)|WebBrowser が現在表示しているリソースの名前を取得します。|  
|[CHtmlView::GetLocationURL](#getlocationurl)|WebBrowser が現在表示しているリソースの URL を取得します。|  
|[CHtmlView::GetMenuBar](#getmenubar)|メニュー バーが表示されるかどうかを判別する値を取得します。|  
|[CHtmlView::GetOffline](#getoffline)|コントロールがオフラインかどうかを判別する値を取得します。|  
|[CHtmlView::GetParentBrowser](#getparentbrowser)|`IDispatch` インターフェイスへのポインターを取得します。 詳細については、次を参照してください。 [IDispatch インターフェイスを実装する](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)です。|  
|[CHtmlView::GetProperty](#getproperty)|指定したオブジェクトに関連付けられているプロパティの現在の値を取得します。|  
|[CHtmlView::GetReadyState](#getreadystate)|Web ブラウザーのオブジェクトの準備完了状態を取得します。|  
|[CHtmlView::GetRegisterAsBrowser](#getregisterasbrowser)|WebBrowser コントロールがターゲット名解決の最上位レベルのブラウザーとして登録されているかどうかを示します。|  
|[CHtmlView::GetRegisterAsDropTarget](#getregisterasdroptarget)|WebBrowser コントロールがナビゲーションのドロップ先として登録されているかどうかを示します。|  
|[CHtmlView::GetSilent](#getsilent)|ダイアログ ボックスを表示できるかどうかを示します。|  
|[CHtmlView::GetSource](#getsource)|Web ページの HTML ソース コード。|  
|[CHtmlView::GetStatusBar](#getstatusbar)|Internet Explorer のステータス バーが表示されているかどうかを示します。 (WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。)|  
|[CHtmlView::GetTheaterMode](#gettheatermode)|WebBrowser コントロールがシアター モードかどうかを示します。|  
|[CHtmlView::GetToolBar](#gettoolbar)|ツール バーが表示されているかどうかを判別する値を取得します。|  
|[CHtmlView::GetTop](#gettop)|Internet Explorer のメイン ウィンドウの上端の画面座標を取得します。|  
|[CHtmlView::GetTopLevelContainer](#gettoplevelcontainer)|現在のオブジェクトが WebBrowser コントロールの最上位のコンテナーかどうかを示す値を取得します。|  
|[CHtmlView::GetType](#gettype)|ドキュメント オブジェクトの型名を取得します。|  
|[CHtmlView::GetVisible](#getvisible)|オブジェクトの表示または非表示を示す値を取得します。|  
|[CHtmlView::GetWidth](#getwidth)|Internet Explorer のメイン ウィンドウの幅を取得します。|  
|[CHtmlView::GoBack](#goback)|履歴の一覧の前の項目に移動します。|  
|[CHtmlView::GoForward](#goforward)|履歴の一覧の次の項目に移動します。|  
|[CHtmlView::GoHome](#gohome)|現在のホーム ページまたはスタート ページに移動します。|  
|[CHtmlView::GoSearch](#gosearch)|現在の検索ページに移動します。|  
|[CHtmlView::LoadFromResource](#loadfromresource)|WebBrowser コントロールのリソースを読み込みます。|  
|[CHtmlView::Navigate](#navigate)|URL で識別されるリソースに移動します。|  
|[CHtmlView::Navigate2](#navigate2)|URL で識別されるリソースまたは完全なパスで識別されるファイルに移動します。|  
|[CHtmlView::OnBeforeNavigate2](#onbeforenavigate2)|指定された WebBrowser 内での移動 (ウィンドウかフレームセット要素上で) が起こる前に呼び出されます。|  
|[CHtmlView::OnCommandStateChange](#oncommandstatechange)|Web ブラウザー コマンドの有効な状態が変更されたことをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnDocumentComplete](#ondocumentcomplete)|ドキュメントが `READYSTATE_COMPLETE` 状態に達していることをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnDocWindowActivate](#ondocwindowactivate)|Internet Explorer または MSHTML 実装から呼び出される[IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281)コンテナーのドキュメント ウィンドウがアクティブ化または非アクティブ化されたときにアクティブなインプレース オブジェクトに通知します。|  
|[CHtmlView::OnDownloadBegin](#ondownloadbegin)|ナビゲーション操作が開始中であることをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnDownloadComplete](#ondownloadcomplete)|ナビゲーション操作が終了したとき、中止したとき、または失敗したときに呼び出されます。|  
|[CHtmlView::OnEnableModeless](#onenablemodeless)|コンテナーがモーダル ダイアログ ボックスを作成または破棄するときに、モードレス ダイアログ ボックスを有効または無効にするために呼び出されます。|  
|[CHtmlView::OnFilterDataObject](#onfilterdataobject)|ホストが Internet Explorer または MSHTML のデータ オブジェクトを置き換えできるように Internet Explorer または MSHTML によってホスト上で呼び出されます。|  
|[CHtmlView::OnFrameWindowActivate](#onframewindowactivate)|呼び出される[IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969)フレーム ウィンドウがアクティブまたは非アクティブ化にコンテナーの最上位レベル オブジェクトを通知します。|  
|[CHtmlView::OnFullScreen](#onfullscreen)|FullScreen プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnGetDropTarget](#ongetdroptarget)|別の方法を提供するホストを許可するようにドロップ先として使用している場合は、Internet Explorer または MSHTML により呼び出される[IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)します。|  
|[CHtmlView::OnGetExternal](#ongetexternal)|ホストの `IDispatch` インターフェイスを取得するために Internet Explorer または MSHTML によって呼び出されます。|  
|[CHtmlView::OnGetHostInfo](#ongethostinfo)|Internet Explorer または MSHTML ホストの UI 機能を取得します。|  
|[CHtmlView::OnGetOptionKeyPath](#ongetoptionkeypath)|Internet Explorer または MSHTML がユーザーの設定を格納しているレジストリ キーを返します。|  
|[CHtmlView::OnHideUI](#onhideui)|Internet Explorer または MSHTML がメニューやツール バーを削除するときに呼び出されます。|  
|[CHtmlView::OnMenuBar](#onmenubar)|MenuBar プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnNavigateComplete2](#onnavigatecomplete2)|ハイパーリンクへの移動 (ウィンドウかフレームセット要素上で) が終了した後で呼び出されます。|  
|[CHtmlView::OnNavigateError](#onnavigateerror)|ハイパーリンクへの移動が失敗したときに、フレームワークによって呼び出されます。|  
|[CHtmlView::OnNewWindow2](#onnewwindow2)|リソースを表示する新しいウィンドウが作成されるときに呼び出されます。|  
|[CHtmlView::OnProgressChange](#onprogresschange)|ダウンロード操作の進行が更新されたことをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnPropertyChange](#onpropertychange)|アプリケーションに通知するために呼び出されますが、 [PutProperty](#putproperty)メソッドには、プロパティの値が変更されました。|  
|[CHtmlView::OnQuit](#onquit)|Internet Explorer アプリケーションが終了しそうなときに、アプリケーションに通知するために呼び出されます。 (Internet Explorer のみに適用)|  
|[CHtmlView::OnResizeBorder](#onresizeborder)|Internet Explorer または MSHTML 実装から呼び出される[IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053)、境界領域のサイズを変更する必要のあるオブジェクトを警告します。|  
|[CHtmlView::OnShowContextMenu](#onshowcontextmenu)|コンテキスト メニューを表示しようとしているときに、Internet Explorer または MSHTML から呼び出されます。|  
|[CHtmlView::OnShowUI](#onshowui)|Internet Explorer または MSHTML がメニューやツール バーを表示する前に呼び出されます。|  
|[CHtmlView::OnStatusBar](#onstatusbar)|StatusBar プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnStatusTextChange](#onstatustextchange)|WebBrowser コントロールと関連付けられているステータス バーのテキストが変更されたことをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnTheaterMode](#ontheatermode)|TheaterMode プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnTitleChange](#ontitlechange)|WebBrowser コントロールのドキュメントのタイトルが使用できるようになるかどうか、また変更するかどうかを、アプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnToolBar](#ontoolbar)|ToolBar プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnTranslateAccelerator](#ontranslateaccelerator)|Internet Explorer または MSHTML により呼び出されるときに[IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360)または[IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756)コンテナーのメッセージ キューからのメニューのアクセラレータ キー メッセージを処理します。|  
|[CHtmlView::OnTranslateUrl](#ontranslateurl)|読み込む URL をホストが変更できるようにするため、Internet Explorer または MSHTML によって呼び出されます。|  
|[CHtmlView::OnUpdateUI](#onupdateui)|コマンドの状態が変化したことをホストに通知します。|  
|[CHtmlView::OnVisible](#onvisible)|WebBrowser コントロールのウィンドウが表示または隠す状態になるべきときに呼び出されます。|  
|[CHtmlView::PutProperty](#putproperty)|指定したオブジェクトに関連付けられているプロパティの値を設定します。|  
|[CHtmlView::QueryFormsCommand](#queryformscommand)|ユーザー インターフェイスのイベントによって生成された&1; つ以上のコマンドの状態を調べるためにクエリを実行します。|  
|[CHtmlView::QueryStatusWB](#querystatuswb)|WebBrowser コントロールによって処理されているコマンドの状態を調べるためにクエリを実行します。|  
|[CHtmlView::Refresh](#refresh)|現在のファイルを再読み込みします。|  
|[CHtmlView::Refresh2](#refresh2)|現在のファイルを再読み込みし、必要に応じて `pragma:nocache` ヘッダーが送信されないようにします。|  
|[CHtmlView::SetAddressBar](#setaddressbar)|Internet Explorer のオブジェクトのアドレス バーを表示または非表示にします。 (WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。)|  
|[CHtmlView::SetFullScreen](#setfullscreen)|コントロールが全画面表示モードと標準ウィンドウ モードのどちらで動作するかを決定する値を設定します。 (WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。)|  
|[CHtmlView::SetHeight](#setheight)|Internet Explorer のメイン ウィンドウの高さを設定します。|  
|[CHtmlView::SetLeft](#setleft)|Internet Explorer のメイン ウィンドウの水平方向の位置を設定します。|  
|[CHtmlView::SetMenuBar](#setmenubar)|コントロールのメニュー バーを表示するかどうかを決定する値を設定します。 (WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。)|  
|[CHtmlView::SetOffline](#setoffline)|コントロールがオフラインであるかどうかを決定する値を設定します。|  
|[CHtmlView::SetRegisterAsBrowser](#setregisterasbrowser)|WebBrowser コントロールがターゲット名解決の最上位レベルのブラウザーとして登録されているかどうかを示す値を設定します。|  
|[CHtmlView::SetRegisterAsDropTarget](#setregisterasdroptarget)|WebBrowser コントロールがナビゲーションのドロップ先として登録されているかどうかを示す値を設定します。|  
|[CHtmlView::SetSilent](#setsilent)|コントロールがダイアログ ボックスを表示するかどうかを決定する値を設定します。|  
|[CHtmlView::SetStatusBar](#setstatusbar)|Internet Explorer のステータス バーを表示するかどうかを決定する値を設定します。 (WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。)|  
|[CHtmlView::SetTheaterMode](#settheatermode)|WebBrowser コントロールがシアター モードかどうかを示す値を設定します。|  
|[CHtmlView::SetToolBar](#settoolbar)|コントロールのツール バーを表示するかどうかを決定する値を設定します。 (WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。)|  
|[CHtmlView::SetTop](#settop)|Internet Explorer のメイン ウィンドウの水平方向の位置を設定します。|  
|[CHtmlView::SetVisible](#setvisible)|オブジェクトの表示または非表示を示す値を設定します。|  
|[CHtmlView::SetWidth](#setwidth)|Internet Explorer のメイン ウィンドウの幅を設定します。|  
|[CHtmlView::Stop](#stop)|ファイルを開くことを中止します。|  
  
## <a name="remarks"></a>コメント  
 WebBrowser コントロールは、World Wide Web 上のサイト、およびローカル ファイル システム内とネットワーク上のフォルダーをユーザーが閲覧できるウィンドウです。 WebBrowser コントロールは、ハイパーリンクと Uniform Resource Locator (URL) のナビゲーションをサポートし、履歴一覧を管理します。  
  
## <a name="using-the-chtmlview-class-in-an-mfc-application"></a>MFC アプリケーションで CHtmlView クラスを使用する  
 標準の MFC フレームワーク アプリケーション (SDI または MDI ベースのいずれか) では、通常、ビュー オブジェクトは特殊化された一連のクラスから派生します。 これらのクラスはすべて `CView`から派生したものであり、 `CView`によって提供される範囲を超えて特殊機能を提供します。  
  
 `CHtmlView` 上のアプリケーションのビュー クラスに基づいて、ビューに WebBrowser コントロールを提供します。 これにより、アプリケーションを効率的に Web ブラウザーにできます。 Web ブラウザー スタイルのアプリケーションを作成する場合は、MFC アプリケーション ウィザードを使用して、 `CHtmlView` をビュー クラスとして指定する方法をお勧めします。 実装で、MFC アプリケーションで WebBrowser コントロールを使用する方法の詳細については、次を参照してください。 [Web ブラウザー形式のアプリケーションを作成する](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)です。  
  
> [!NOTE]
>  WebBrowser ActiveX コントロール (および `CHtmlView`) は、Internet Explorer 4.0 以降がインストールされている Windows NT Version 4.0 以降で実行されるプログラムでのみ使用できます。  
  
 `CHtmlView`Web にアクセスするアプリケーション向けに設計 (や HTML ドキュメント)。 次の `CHtmlView` メンバー関数は、Internet Explorer のアプリケーションのみに適用されます。 これらの関数は WebBrowser コントロールで成功しますが、視覚的は変化はありません。  
  
- [GetAddressBar](#getaddressbar)  
  
- [GetFullName](#getfullname)  
  
- [GetStatusBar](#getstatusbar)  
  
- [SetAddressBar](#setaddressbar)  
  
- [SetFullScreen](#setfullscreen)  
  
- [SetMenuBar](#setmenubar)  
  
- [SetStatusBar](#setstatusbar)  
  
- [SetToolBar](#settoolbar)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxhtml.h  
  
##  <a name="create"></a>CHtmlView::Create  
 このメンバー関数を作成する WebBrowser コントロールまたはコンテナー、Internet Explorer の実行可能ファイルを呼び出します。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 Windows クラスの名前を示す文字の null で終わる文字列へのポインター。 クラス名に登録されている任意の名前を指定できます、 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass)グローバル関数、または**RegisterClass** Windows の機能です。 場合**NULL**、定義済みの既定値を使用して[CFrameWnd](../../mfc/reference/cframewnd-class.md)属性です。  
  
 `lpszWindowName`  
 ウィンドウの名前を表す文字の null で終わる文字列へのポインター。  
  
 `dwStyle`  
 ウィンドウのスタイル属性を指定します。 既定では、 **WS_VISIBLE**と**WS_CHILD**ウィンドウ スタイルを設定します。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとウィンドウの位置を指定します。 `rectDefault`値により、Windows のサイズと新しいウィンドウの位置を指定します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 ビューの ID 番号。 既定では、設定**AFX_IDW_PANE_FIRST**します。  
  
 `pContext`  
 ポインター、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)します。 **NULL**既定です。  
  
##  <a name="createcontrolsite"></a>CHtmlView::CreateControlSite  
 フォーム上のコントロールをホストするコントロール サイトのインスタンスを作成するために使用する、オーバーライド可能なメソッド。  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT nID,  
    REFCLSID clsid);
```  
  
### <a name="parameters"></a>パラメーター  
 `pContainer`  
 ポインター、[メンバー](../../mfc/reference/colecontrolcontainer-class.md)コントロールを含むオブジェクト。  
  
 `ppSite`  
 ポインターへのポインター、[メンバー](../../mfc/reference/colecontrolsite-class.md)オブジェクト、コントロールのサイトを提供します。  
  
 `nID`  
 ホストされるコントロールの識別子です。  
  
 `clsid`  
 ホストされるコントロールの CLSID  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 コントロール サイト クラスのインスタンスを返すには、このメンバー関数をオーバーライドすることができます。  
  
##  <a name="execformscommand"></a>CHtmlView::ExecFormsCommand  
 指定されたコマンドを `IOleCommandTarget::Exec` メソッドを使用して実行します。  
  
```  
HRESULT ExecFormsCommand(
    DWORD dwCommandID,  
    VARIANT* pVarIn,  
    VARIANT* pVarOut);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCommandID`  
 実行するコマンド。 このコマンドに属している必要があります、 **CMDSETID3_Forms3**グループです。  
  
 *pVarIn*  
 ポインター、 **VARIANT**入力引数を含む構造体。 できる**NULL**します。  
  
 *pVarOut*  
 ポインター、 **VARIANT**コマンドの出力を受け取る構造体。 できる**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。 使用可能な値の完全な一覧については、次を参照してください。 [iolecommandtarget::exec](http://msdn.microsoft.com/library/windows/desktop/ms690300)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 **ExecFormsCommand**の動作を実装、 [iolecommandtarget::exec](http://msdn.microsoft.com/library/windows/desktop/ms690300)メソッドです。  
  
##  <a name="execwb"></a>CHtmlView::ExecWB  
 WebBrowser または Internet Explorer でコマンドを実行するには、このメンバー関数を呼び出します。  
  
```  
void ExecWB(
    OLECMDID cmdID,  
    OLECMDEXECOPT cmdexecopt,  
    VARIANT* pvaIn,  
    VARIANT* pvaOut);
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 実行するコマンド。  
  
 *cmdexecopt*  
 コマンドを実行するため、オプションを設定します。  
  
 `pvaIn`  
 コマンドの入力引数を指定するバリアント値。  
  
 *pvaOut*  
 コマンドの出力引数を指定するバリアント値。  
  
### <a name="remarks"></a>コメント  
 参照してください[IWebBrowser2::ExecWB](https://msdn.microsoft.com/library/aa752117.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getaddressbar"></a>CHtmlView::GetAddressBar  
 Internet Explorer のアドレス バーを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetAddressBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アドレス バーを表示する場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer に適用されます。 WebBrowser コントロールでこの呼び出しを使用する場合に返されません、エラーが、この呼び出しは無視されます。  
  
##  <a name="getapplication"></a>CHtmlView::GetApplication  
 WebBrowser コントロールを含むアプリケーションでサポートされるオートメーション オブジェクトを取得するには、このメンバー関数を呼び出します。  
  
```  
LPDISPATCH GetApplication() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`IDispatch`作業中のドキュメント オブジェクトのインターフェイスです。 詳細については、次を参照してください。 [IDispatch インターフェイスを実装する](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)です。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getbusy"></a>CHtmlView::GetBusy  
 WebBrowser コントロールは、ナビゲーション プロパティまたはダウンロード操作に関与しているかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetBusy() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、web ブラウザーがビジー状態です。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getcontainer"></a>CHtmlView::GetContainer  
 Web ブラウザーのコンテナーに評価されるオブジェクトを取得するには、このメンバー関数を呼び出します。  
  
```  
LPDISPATCH GetContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`IDispatch`作業中のドキュメント オブジェクトのインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getfullname"></a>CHtmlView::GetFullName  
 Internet Explorer が現在表示されているファイルの完全パスを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)現在表示されているファイルの名前とパスを含むオブジェクト。 パスとファイル名が存在しない場合`GetFullName`は空白を返します`CString`します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer に適用されます。 WebBrowser コントロールでこの呼び出しを使用する場合に返されません、エラーが、この呼び出しは無視されます。  
  
##  <a name="getfullscreen"></a>CHtmlView::GetFullScreen  
 WebBrowser コントロールを全画面表示モードまたは標準ウィンドウ モードで動作するかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetFullScreen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 WebBrowser が全画面表示モードで動作している場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 全画面表示モードでは、Internet Explorer のメイン ウィンドウを最大化し、ステータス バー、ツールバー、メニュー バー、およびタイトル バーを非表示します。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getheight"></a>CHtmlView::GetHeight  
 WebBrowser コントロールのフレーム ウィンドウのピクセル単位の高さを取得するには、このメンバー関数を呼び出します。  
  
```  
long GetHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのフレーム ウィンドウ高さ (ピクセル単位)。  
  
##  <a name="gethtmldocument"></a>CHtmlView::GetHtmlDocument  
 アクティブなドキュメントの HTML ドキュメントを取得するには、このメンバー関数を呼び出します。  
  
```  
LPDISPATCH GetHtmlDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`IDispatch`作業中のドキュメント オブジェクトのインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getleft"></a>CHtmlView::GetLeft  
 WebBrowser コントロールの内側の左端とコンテナーの左端の間の距離を取得するには、このメンバー関数を呼び出します。  
  
```  
long GetLeft() const;  
```  
  
### <a name="return-value"></a>戻り値  
 左端の距離 (ピクセル単位)。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getlocationname"></a>CHtmlView::GetLocationName  
 このメンバー関数を呼び出して、web ブラウザーに表示されているリソースの名前を取得します。  
  
```  
CString GetLocationName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) web ブラウザーに表示されているリソースの名前を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 リソースが World Wide Web 上の HTML ページの場合は、名前はそのページのタイトルです。 リソースがフォルダーまたはネットワークまたはローカル コンピューター上のファイルの場合、名前は UNC またはフォルダーまたはファイルの完全なパスです。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getlocationurl"></a>CHtmlView::GetLocationURL  
 WebBrowser コントロールが現在表示されているリソースの URL を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetLocationURL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) web ブラウザーに表示されているリソースの URL を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 リソースがフォルダーまたはネットワークまたはローカル コンピューター上のファイルの場合、名前は UNC またはフォルダーまたはファイルの完全なパスです。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getmenubar"></a>CHtmlView::GetMenuBar  
 メニュー バーが表示されているかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetMenuBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー バーを表示する場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getoffline"></a>CHtmlView::GetOffline  
 Web ブラウザーがオフラインで動作するかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetOffline() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Web ブラウザーが現在オフラインの場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getparentbrowser"></a>CHtmlView::GetParentBrowser  
 WebBrowser コントロールの親オブジェクトへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
LPDISPATCH GetParentBrowser() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `IDispatch` WebBrowser コントロールの親であるオブジェクトのインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getproperty"></a>CHtmlView::GetProperty  
 このメンバー関数を呼び出して、コントロールに関連付けられているプロパティの値を取得します。  
  
```  
BOOL GetProperty(
    LPCTSTR lpszProperty,  
    CString& strValue);  
  
COleVariant GetProperty(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProperty`  
 取得するプロパティを含む文字列へのポインター。  
  
 `strValue`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)プロパティの現在の値を受け取るオブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は&0; 以外の最初のバージョンでそれ以外の場合&0; を返します。 2 番目の形式で、 [COleVariant](../../mfc/reference/colevariant-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getreadystate"></a>CHtmlView::GetReadyState  
 WebBrowser オブジェクトの準備完了状態を取得するには、このメンバー関数を呼び出します。  
  
```  
READYSTATE GetReadyState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [READYSTATE](https://msdn.microsoft.com/library/aa768362.aspx)値に設定する」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getregisterasbrowser"></a>CHtmlView::GetRegisterAsBrowser  
 WebBrowser オブジェクトがターゲットの名前解決のための最上位レベルのブラウザーとして登録されているかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetRegisterAsBrowser() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ブラウザーが最上位レベルのブラウザーとして登録されている場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getregisterasdroptarget"></a>CHtmlView::GetRegisterAsDropTarget  
 WebBrowser コントロールがナビゲーションのドロップ先として登録されているかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetRegisterAsDropTarget() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ブラウザーがドロップ ターゲットとして登録されている場合は&0; 以外それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getsilent"></a>CHtmlView::GetSilent  
 WebBrowser コントロールのすべてのダイアログ ボックスを表示できるかどうかを判断するのには、このメンバー関数を呼び出します。  
  
```  
BOOL GetSilent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 WebBrowser コントロールからダイアログ ボックスを表示できない場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getsource"></a>CHtmlView::GetSource  
 Web ページの HTML ソース コードを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetSource(CString& strRef);
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="parameters"></a>パラメーター  
 `refString`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ソース コードを保持します。  
  
### <a name="remarks"></a>コメント  
 この関数は、ソース コードが返されますが、Internet Explorer で、ソースの表示 コマンドに対応する`CString`です。  
  
##  <a name="getstatusbar"></a>CHtmlView::GetStatusBar  
 WebBrowser コントロールがステータス バーを表示するかどうかを指定するのには、このメンバー関数を呼び出します。  
  
```  
BOOL GetStatusBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ステータス バーを表示する場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer に適用されます。 WebBrowser コントロールでこの呼び出しを使用する場合に返されません、エラーが、この呼び出しは無視されます。  
  
##  <a name="gettheatermode"></a>CHtmlView::GetTheaterMode  
 Web ブラウザーがシアター モードかどうかを確認するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetTheaterMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Web ブラウザーがシアター モードである場合は&0; 以外それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 シアター モードで web ブラウザーがある場合は、ブラウザーのメイン ウィンドウが画面全体を占めるおよびナビゲーション ツールの最小限のセットを含むツールバーが表示されたら、画面の右上隅のステータス バーが表示されます。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="gettoolbar"></a>CHtmlView::GetToolBar  
 ツールバーを表示するかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
int GetToolBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツールバーを表示するかどうかを示す値。 ツールバーを表示する場合は&0; 以外。それ以外の場合&0; を返します。  
  
##  <a name="gettop"></a>CHtmlView::GetTop  
 WebBrowser コントロールのメイン ウィンドウの上端の画面座標を取得するには、このメンバー関数を呼び出します。  
  
```  
long GetTop() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メイン ウィンドウの上端の画面座標を受け取る変数のアドレスです。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="gettoplevelcontainer"></a>CHtmlView::GetTopLevelContainer  
 Internet Explorer が WebBrowser コントロールの最上位のコンテナーであるかどうかを確認するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetTopLevelContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値は、コンテナーは最上位のコンテナーです。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="gettype"></a>CHtmlView::GetType  
 含まれているアクティブなドキュメントの型名を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)含まれているアクティブなドキュメントの種類名を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getvisible"></a>CHtmlView::GetVisible  
 格納されているオブジェクトが表示されているかどうかの決定には、このメンバー関数を呼び出します。  
  
```  
BOOL GetVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトを表示する場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="getwidth"></a>CHtmlView::GetWidth  
 Internet Explorer のメイン ウィンドウの幅を取得します。  
  
```  
long GetWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、ウィンドウの現在の幅。  
  
##  <a name="goback"></a>CHtmlView::GoBack  
 旧バージョンとの&1; つの履歴リスト アイテムを移動します。  
  
```  
void GoBack();
```  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="goforward"></a>CHtmlView::GoForward  
 履歴一覧の次のアイテムを移動します。  
  
```  
void GoForward();
```  
  
##  <a name="gohome"></a>CHtmlView::GoHome  
 Internet Explorer の [インターネット オプション] ダイアログ ボックス、またはコントロール パネルからアクセスする [インターネットのプロパティ] ダイアログ ボックスで指定した、現在のホーム ページまたはスタート ページに移動します。  
  
```  
void GoHome();
```  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="gosearch"></a>CHtmlView::GoSearch  
 現在の検索ページを Internet Explorer のインターネット オプション ダイアログ ボックスまたはインターネットのプロパティ ダイアログ ボックスで指定されたコントロール パネルからアクセスに移動します。  
  
```  
void GoSearch();
```  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="loadfromresource"></a>CHtmlView::LoadFromResource  
 WebBrowser コントロールに指定したリソースを読み込むには、このメンバー関数を呼び出します。  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResource`  
 読み込むリソースの名前を含む文字列へのポインター。  
  
 `nRes`  
 読み込むリソースの名前を格納するバッファーの ID。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="navigate"></a>CHtmlView::Navigate  
 このメンバー関数を呼び出して、URL によって識別されるリソースに移動します。  
  
```  
void Navigate(
    LPCTSTR URL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *URL*  
 移動先の URL を含む呼び出し元が割り当てた文字列またはに表示されるファイルの完全パス。  
  
 `dwFlags`  
 履歴一覧にリソースを追加するかどうか、読み取りや、キャッシュから作成するかどうかと、新しいウィンドウで、リソースを表示するかどうかを指定する変数のフラグです。 変数で定義される値の組み合わせが可能、[変数には](https://msdn.microsoft.com/library/aa768360.aspx)列挙します。  
  
 `lpszTargetFrameName`  
 リソースを表示するフレームの名前を含む文字列へのポインター。  
  
 `lpszHeaders`  
 サーバーに送信する HTTP ヘッダーを指定する値へのポインター。 これらのヘッダーは、Internet Explorer の既定のヘッダーに追加されます。 ヘッダーでは、サーバー、または、状態コードに渡されるデータの種類、サーバーのために必要なアクションとしてなどを指定できます。 場合、このパラメーターは無視されます*URL* HTTP URL ではありません。  
  
 `lpvPostData`  
 HTTP POST のトランザクションに送信するデータへのポインター。 たとえば、POST トランザクションを使用して、HTML フォームによって収集されたデータを送信します。 このパラメーターは、post データを指定しない場合**Navigate** HTTP GET のトランザクションを発行します。 場合、このパラメーターは無視されます*URL* HTTP URL ではありません。  
  
 `dwPostDataLen`  
 HTTP POST のトランザクションに送信するデータ。 たとえば、POST トランザクションを使用して、HTML フォームによって収集されたデータを送信します。 このパラメーターは、post データを指定しない場合**Navigate** HTTP GET のトランザクションを発行します。 場合、このパラメーターは無視されます*URL* HTTP URL ではありません。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="navigate2"></a>CHtmlView::Navigate2  
 このメンバー関数を呼び出して、完全なパスで指定されたファイルまたは URL によって識別されるリソースに移動します。  
  
```  
void Navigate2(
    LPITEMIDLIST pIDL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags,  
    CByteArray& baPostedData,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeader = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pIDL*  
 ポインター、 [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321)構造体。  
  
 `dwFlags`  
 履歴一覧にリソースを追加するかどうか、読み取りや、キャッシュから作成するかどうかと、新しいウィンドウで、リソースを表示するかどうかを指定する変数のフラグです。 変数で定義される値の組み合わせが可能、[変数には](https://msdn.microsoft.com/library/aa768360.aspx)列挙します。  
  
 `lpszTargetFrameName`  
 リソースを表示するフレームの名前を含む文字列へのポインター。  
  
 `lpszURL`  
 URL を含む文字列へのポインター。  
  
 `lpvPostData`  
 HTTP POST のトランザクションに送信するデータ。 たとえば、POST トランザクションを使用して、HTML フォームによって収集されたデータを送信します。 このパラメーターは、post データを指定しない場合`Navigate2`HTTP GET のトランザクションを発行します。 場合、このパラメーターは無視されます*URL* HTTP または HTTPS URL ではありません。  
  
 `dwPostDataLen`  
 データのバイト長が指す、`lpvPostData`パラメーター。  
  
 `lpszHeaders`  
 サーバーに送信する HTTP または HTTPS のヘッダーを指定する値へのポインター。 これらのヘッダーは、Internet Explorer の既定のヘッダーに追加されます。 ヘッダーでは、サーバー、または、状態コードに渡されるデータの種類、サーバーのために必要なアクションとしてなどを指定できます。 場合、このパラメーターは無視されます*URL* HTTP または HTTPS URL ではありません。  
  
 `baPostedData`  
 参照、 [CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を拡張、 **Navigate**パラメーターによって表されているデスクトップやマイ コンピューター などの特別なフォルダーの参照をサポートすることによって、メンバー関数*pIDL*します。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCHtmlHttp&#7;](../../mfc/reference/codesnippet/cpp/chtmlview-class_1.cpp)]  
  
##  <a name="onbeforenavigate2"></a>CHtmlView::OnBeforeNavigate2  
 このメンバー関数は、ナビゲーションが web ブラウザーで発生する前に、イベントが発生するために、フレームワークによって呼び出されます。  
  
```  
virtual void OnBeforeNavigate2(
    LPCTSTR lpszURL,  
    DWORD nFlags,  
    LPCTSTR lpszTargetFrameName,  
    CByteArray& baPostedData,  
    LPCTSTR lpszHeaders,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszURL`  
 移動する URL を含む文字列へのポインター。  
  
 `nFlags`  
 将来使用するために予約されています。  
  
 `lpszTargetFrameName`  
 リソースを表示するフレームの名前を表す文字列または**NULL**リソースの対象となる名前付きフレームがない場合。  
  
 `baPostedData`  
 参照、 `CByteArray` HTTP POST トランザクションを使用している場合は、サーバーに送信するデータを格納します。  
  
 `lpszHeaders`  
 サーバー (HTTP Url) に送信する追加の HTTP ヘッダーを含む文字列へのポインター。 ヘッダーでは、サーバー、または、状態コードに渡されるデータの種類、サーバーのために必要なアクションとしてなどを指定できます。  
  
 `pbCancel`  
 キャンセル フラグへのポインター。 アプリケーションでは、ナビゲーション操作を取り消すか続行を許可するようにゼロに&0; 以外に、このパラメーターを設定できます。  
  
##  <a name="oncommandstatechange"></a>CHtmlView::OnCommandStateChange  
 このメンバー関数は、web ブラウザーのコマンドの有効状態が変更されたことをアプリケーションに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnCommandStateChange(
    long nCommand,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 *%t%7*  
 有効な状態が変化したコマンドの識別子です。  
  
 `bEnable`  
 有効な状態です。 コマンドが有効になっては無効になっている場合は&0; である場合は、このパラメーターは&0; 以外です。  
  
##  <a name="ondocumentcomplete"></a>CHtmlView::OnDocumentComplete  
 到達したドキュメントをアプリケーションに通知するためにフレームワークによって呼び出されます、`READYSTATE_COMPLETE`状態です。  
  
```  
virtual void OnDocumentComplete(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszURL`  
 URL、UNC に評価される文字列へのポインターはファイル名、または移動先 PIDL (アイテム id リストへのポインター)。  
  
### <a name="remarks"></a>コメント  
 すべてのフレームが各フレームを起動するが、このイベントを発生させる、 [OnDownloadBegin](#ondownloadbegin) 、対応するイベントは発生`OnDocumentComplete`イベントです。  
  
 示された URL`lpszURL`ブラウザーは、この URL は、正規化された、修飾 URL であるために移動が指示された URL から異なる可能性があります。 たとえば、アプリケーションへの呼び出しで"www.microsoft.com"の URL で指定する[Navigate](#navigate)または[Navigate2](#navigate2)、渡された URL `OnNavigateComplete2` "http://www.microsoft.com/"になります。 また、サーバーが別の URL にブラウザーをリダイレクトする場合、ここで、リダイレクトされた URL が反映されます。  
  
##  <a name="ondocwindowactivate"></a>CHtmlView::OnDocWindowActivate  
 コンテナーのドキュメント ウィンドウがアクティブ化または非アクティブ化されたときにアクティブなインプレース オブジェクトに通知する、 **IOleInPlaceActiveObject::OnDocWindowActivate**の Internet Explorer または MSHTML の実装から呼び出されます。  
  
```  
virtual HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 `fActivate`  
 ドキュメント ウィンドウの状態を示します。 この値が&0; 以外の場合は、ウィンドウがアクティブ化されています。 この値が&0; の場合は、ウィンドウを非アクティブ化します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、それ以外の場合は OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnDocWindowActivate`に対応するため、 `OnDocWindowActivate` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="ondownloadbegin"></a>CHtmlView::OnDownloadBegin  
 このメンバー関数は、ドキュメントのダウンロードを開始するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDownloadBegin();
```  
  
### <a name="remarks"></a>コメント  
 このイベントは発生直後に、 [OnBeforeNavigate2](#onbeforenavigate2)イベント、ナビゲーションが取り消された場合を除き、します。 このイベントには、アニメーションまたはコンテナーが表示する必要がある「ビジー」を示す値を接続する必要があります。  
  
##  <a name="ondownloadcomplete"></a>CHtmlView::OnDownloadComplete  
 このメンバー関数が終了したら、ナビゲーション操作が停止されると、か、失敗したことを示すために、フレームワークによって呼び出されます。  
  
```  
virtual void OnDownloadComplete();
```  
  
##  <a name="onenablemodeless"></a>CHtmlView::OnEnableModeless  
 Internet Explorer または MSHTML にモーダル UI が表示されるときに呼び出されます。  
  
```  
virtual HRESULT OnEnableModeless(BOOL fEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `fEnable`  
 ホストのモードレス ダイアログ ボックスを有効または無効になっているかどうかを示します。 この値が&0; 以外の場合は、モードレス ダイアログ ボックスが有効になります。 この値が&0; の場合は、モードレス ダイアログ ボックスが無効になります。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、それ以外の場合は OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 有効またはコンテナーを作成するか、モーダル ダイアログ ボックスを破棄するときは、モードレス ダイアログ ボックスを無効にします。 オーバーライド`OnEnableModeless`に対応するため、 `EnableModeless` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="onfilterdataobject"></a>CHtmlView::OnFilterDataObject  
 ホストが Internet Explorer または MSHTML のデータ オブジェクトを置き換えできるように Internet Explorer または MSHTML によってホスト上で呼び出されます。  
  
```  
virtual HRESULT OnFilterDataObject(
    LPDATAOBJECT pDataObject,  
    LPDATAOBJECT* ppDataObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 アドレス、 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Internet Explorer または MSHTML で提供されるインターフェイスです。  
  
 *ppDataObject*  
 受信するアドレスを`IDataObject`ホストによって提供されるインターフェイス ポインター。 このパラメーターの内容は、必ずに初期化する**NULL**メソッドが失敗した場合でも、します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`データ オブジェクトを置き換えた場合**S_FALSE**データ オブジェクトが置き換えられない場合や、エラーが発生した場合の OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnFilterDataObject`に対応するため、 `FilterDataObject` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="onframewindowactivate"></a>CHtmlView::OnFrameWindowActivate  
 呼び出される[IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969)フレーム ウィンドウがアクティブまたは非アクティブ化にコンテナーの最上位レベル オブジェクトを通知します。  
  
```  
virtual HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 `fActivate`  
 コンテナーの最上位のフレーム ウィンドウの状態を示します。 この値が&0; 以外の場合は、ウィンドウがアクティブ化されています。 この値が&0; の場合は、ウィンドウを非アクティブ化します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、それ以外の場合は OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnFrameWindowActivate`に対応するため、 `OnFrameWindowActivate` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="onfullscreen"></a>CHtmlView::OnFullScreen  
 フレームワークによって呼び出されますときに、[全画面表示](https://msdn.microsoft.com/library/aa752119.aspx)プロパティが変更されました。  
  
```  
virtual void OnFullScreen(BOOL bFullScreen);
```  
  
### <a name="parameters"></a>パラメーター  
 *bFullScreen*  
 Internet Explorer が全画面表示モードである場合は&0; 以外それ以外の場合はゼロ。  
  
##  <a name="ongetdroptarget"></a>CHtmlView::OnGetDropTarget  
 別の方法を提供するホストを許可するようにドロップ先として使用している場合は、Internet Explorer または MSHTML により呼び出される`IDropTarget`です。  
  
```  
virtual HRESULT OnGetDropTarget(
    LPDROPTARGET pDropTarget,  
    LPDROPTARGET* ppDropTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDropTarget`  
 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)を使用するか、Internet Explorer MSHTML を提案します。  
  
 `ppDropTarget`  
 アドレス、`IDropTarget`を受け取る、`IDropTarget`インターフェイス ポインターを提供します。  
  
### <a name="return-value"></a>戻り値  
 参照してください[IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]のリターン コードの一覧です。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnGetDropTarget`に対応するため、 `GetDropTarget` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="ongetexternal"></a>CHtmlView::OnGetExternal  
 ホストの `IDispatch` インターフェイスを取得するために Internet Explorer または MSHTML によって呼び出されます。  
  
```  
virtual HRESULT OnGetExternal(LPDISPATCH* lppDispatch);
```  
  
### <a name="parameters"></a>パラメーター  
 *lppDispatch*  
 受信するアドレスへのポインター、`IDispatch`ホスト アプリケーションのインターフェイス ポインター。 ホストは、オートメーション インターフェイスを公開する場合は、このパラメーターを通じて Internet Explorer または MSHTML への参照を提供できます。 このパラメーターの内容は、必ずに初期化する**NULL**メソッドが失敗した場合でも、します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、それ以外の場合は OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnGetExternal`に対応するため、 `GetExternal` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="ongethostinfo"></a>CHtmlView::OnGetHostInfo  
 Internet Explorer または MSHTML ホストの UI 機能を取得します。  
  
```  
virtual HRESULT OnGetHostInfo(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInfo`  
 アドレス、[受け取る](https://msdn.microsoft.com/library/aa770044.aspx)ホストの UI 機能を受け取る。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、それ以外の場合は OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnGetHostInfo`に対応するため、 `GetHostInfo` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="ongetoptionkeypath"></a>CHtmlView::OnGetOptionKeyPath  
 このメンバー関数を呼び出して Internet Explorer または MSHTML ユーザー設定を格納するレジストリ キーを取得します。  
  
```  
virtual HRESULT OnGetOptionKeyPath(
    LPOLESTR* pchKey,  
    DWORD dwReserved);
```  
  
### <a name="parameters"></a>パラメーター  
 `pchKey`  
 アドレス、`LPOLESTR`ホストが既定のオプションを格納するレジストリ サブキーの文字列を受け取る。 このサブキーは、HKEY_CURRENT_USER キーになります。 使用してこのメモリを割り当てる[CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)します。 呼び出し元のアプリケーションが使用して、このメモリの解放を[CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)します。 このパラメーターは、必ずに初期化する**NULL**メソッドが失敗した場合でも、します。  
  
 `dwReserved`  
 将来使用するために予約されています。 使用されていません。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、または**S_FALSE**それ以外の場合。 場合**S_FALSE**、Internet Explorer または MSHTML の既定値は、独自のユーザー オプション。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnGetOptionKeyPath`に対応するため、 `GetOptionKeyPath` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="onhideui"></a>CHtmlView::OnHideUI  
 メニューおよびツールバーを Internet Explorer または MSHTML が削除すると、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual HRESULT OnHideUI();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、それ以外の場合は OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnHideUI`に対応するため、 `HideUI` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="onmenubar"></a>CHtmlView::OnMenuBar  
 フレームワークによって呼び出されますときに、 [MenuBar](https://msdn.microsoft.com/library/aa752131.aspx)プロパティが変更されました。  
  
```  
virtual void OnMenuBar(BOOL bMenuBar);
```  
  
### <a name="parameters"></a>パラメーター  
 *bMenuBar*  
 Internet Explorer のメニュー バーを表示する場合は&0; 以外。それ以外の場合はゼロ。  
  
##  <a name="onnavigatecomplete2"></a>CHtmlView::OnNavigateComplete2  
 ハイパーリンクへの移動は、(上のウィンドウまたはフレーム セットの要素) が完了した後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnNavigateComplete2(LPCTSTR strURL);
```  
  
### <a name="parameters"></a>パラメーター  
 *strURL*  
 URL に評価される文字列式 UNC ファイル名、または PIDL (アイテム id リストへのポインター) に移動します。  
  
### <a name="remarks"></a>コメント  
 URL パラメーターには、URL の形式がありませんシェル名前空間エンティティの場合 PIDL を指定できます。  
  
 含まれている URL を*strURL*ブラウザーは、この URL は、正規化された、修飾 URL であるために移動が指示された URL から異なる可能性があります。 たとえば、アプリケーションへの呼び出しで"www.microsoft.com"の URL で指定する[Navigate](#navigate)または[Navigate2](#navigate2)、渡された URL `OnNavigateComplete2` "http://www.microsoft.com/"になります。 また、サーバーが別の URL にブラウザーをリダイレクトする場合、ここで、リダイレクトされた URL が反映されます。  
  
##  <a name="onnavigateerror"></a>CHtmlView::OnNavigateError  
 ハイパーリンクへの移動が失敗したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnNavigateError(
    LPCTSTR lpszURL,  
    LPCTSTR lpszFrame,  
    DWORD dwError,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszURL`  
 移動に失敗した URL です。  
  
 *lpszFrame*  
 リソースの表示、またはリソースを対象と名前付きフレームがない場合は NULL にするフレームの名前。  
  
 `dwError`  
 エラー ステータス コード、使用可能な場合です。 可能な HRESULT と HTTP ステータス コードの一覧は、次を参照してください。 [NavigateError イベントのステータス コード。](https://msdn.microsoft.com/library/aa768365.aspx)  
  
 `pbCancel`  
 エラー ページまたはその他の自動検索ナビゲーションをキャンセルするかどうかを指定します。 場合**TRUE** (既定) 場合に、エラー ページまたは自動検索; へのナビゲーションを続行**FALSE**、エラー ページまたは自動検索へのナビゲーションをキャンセルします。  
  
### <a name="remarks"></a>コメント  
 カスタム ナビゲーション エラー処理を行うには、このメソッドをオーバーライドします。  
  
 詳細については、次を参照してください[DWebBrowserEvents2::NavigateError。](https://msdn.microsoft.com/library/aa768286.aspx)  
  
##  <a name="onnewwindow2"></a>CHtmlView::OnNewWindow2  
 新しいウィンドウがリソースを表示するために作成されるときに、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual void OnNewWindow2(
    LPDISPATCH* ppDisp,  
    BOOL* Cancel);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppDisp`  
 必要に応じて、受信するインターフェイス ポインターへのポインター、 `IDispatch` WebBrowser または Internet Explorer の新しいオブジェクトのインターフェイス ポインター。  
  
 `Cancel`  
 キャンセル フラグへのポインター。 アプリケーションでは、ナビゲーション操作を取り消すか続行を許可するようにゼロに&0; 以外に、このパラメーターを設定できます。  
  
### <a name="remarks"></a>コメント  
 このイベントの前に、web ブラウザー内から新しいウィンドウを作成します。  
  
##  <a name="onprogresschange"></a>CHtmlView::OnProgressChange  
 このメンバー関数は、ダウンロード操作の進行状況が更新されたことをアプリケーションに通知するために、フレームワークによって呼び出されます。  
  
```  
virtual void OnProgressChange(
    long nProgress,  
    long nProgressMax);
```  
  
### <a name="parameters"></a>パラメーター  
 *nProgress*  
 表示、または-1 の進行状況が完了すると全体の進行状況の量。  
  
 *nProgressMax*  
 進行状況の最大値。  
  
### <a name="remarks"></a>コメント  
 コンテナーは、これまでにダウンロードされるバイト数を表示したり、プログレス インジケーターを更新する、このイベントによって提供される情報を使用できます。  
  
##  <a name="onpropertychange"></a>CHtmlView::OnPropertyChange  
 アプリケーションに通知するために、フレームワークによって呼び出されますが[PutProperty](#putproperty)がプロパティの値を変更します。  
  
```  
virtual void OnPropertyChange(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProperty`  
 プロパティの名前を含む文字列へのポインター。  
  
##  <a name="onquit"></a>CHtmlView::OnQuit  
 このメンバー関数は、Internet Explorer のアプリケーションが終了する準備が整っているアプリケーションに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnQuit();
```  
  
##  <a name="onresizeborder"></a>CHtmlView::OnResizeBorder  
 Internet Explorer または MSHTML 実装から呼び出される[IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053)、境界領域のサイズを変更する必要のあるオブジェクトを警告します。  
  
```  
virtual HRESULT OnResizeBorder(
    LPCRECT prcBorder,  
    LPOLEINPLACEUIWINDOW pUIWindow,  
    BOOL fFrameWindow);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcBorder`  
 境界領域の新しい外接四角形。  
  
 `pUIWindow`  
 境界が変更されたフレームまたはドキュメント ウィンドウ オブジェクトのインターフェイスへのポインター。  
  
 `fFrameWindow`  
 **TRUE**フレーム ウィンドウを呼び出す場合[IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053)、それ以外の場合**FALSE**します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、それ以外の場合は OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnResizeBorder`に対応するため、 `ResizeBorder` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="onshowcontextmenu"></a>CHtmlView::OnShowContextMenu  
 コンテキスト メニューを表示しようとしているときに、Internet Explorer または MSHTML から呼び出されます。  
  
```  
virtual HRESULT OnShowContextMenu(
    DWORD dwID,  
    LPPOINT ppt,  
    LPUNKNOWN pcmdtReserved,  
    LPDISPATCH pdispReserved);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwID`  
 表示されるコンテキスト メニューの識別子。 参照してください**IDocHostUIHandler::ShowContextMenu**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の値の一覧です。  
  
 `ppt`  
 メニューの画面座標。  
  
 `pcmdtReserved`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797)コマンドの状態を照会し、このオブジェクトに対してコマンドを実行するためのインターフェイスです。  
  
 `pdispReserved`  
 画面座標にあるオブジェクトの IDispatch インターフェイスです。 これにより、詳細なコンテキストを提供する特定のオブジェクトを区別するためにホストできます。  
  
### <a name="return-value"></a>戻り値  
 参照してください[IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の値の一覧です。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnShowContextMenu`に対応するため、 `ShowContextMenu` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="onshowui"></a>CHtmlView::OnShowUI  
 Internet Explorer または MSHTML がメニューやツール バーを表示する前に呼び出されます。  
  
```  
virtual HRESULT OnShowUI(
    DWORD dwID,  
    LPOLEINPLACEACTIVEOBJECT pActiveObject,  
    LPOLECOMMANDTARGET pCommandTarget,  
    LPOLEINPLACEFRAME pFrame,  
    LPOLEINPLACEUIWINDOW pDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwID`  
 将来使用するために予約されています。  
  
 `pActiveObject`  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299)現在アクティブなオブジェクトのインターフェイスです。  
  
 `pCommandTarget`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797)オブジェクトのインターフェイスです。  
  
 `pFrame`  
 [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770)オブジェクトのインターフェイスです。 メニューおよびツールバーに必要です。  
  
 `pDoc`  
 [埋め込み](http://msdn.microsoft.com/library/windows/desktop/ms680716)オブジェクトのインターフェイスです。 ツールバーでは必要です。  
  
### <a name="return-value"></a>戻り値  
 参照してください[IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の値の一覧です。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnShowUI`に対応するため、 `ShowUI` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="onstatusbar"></a>CHtmlView::OnStatusBar  
 フレームワークによって呼び出されますときに、 [StatusBar](https://msdn.microsoft.com/library/aa768270.aspx)プロパティが変更されました。  
  
```  
virtual void OnStatusBar(BOOL bStatusBar);
```  
  
### <a name="parameters"></a>パラメーター  
 *bStatusBar*  
 Internet Explorer のステータス バーが表示される場合は&0; 以外か、それ以外の場合は&0; です。  
  
##  <a name="onstatustextchange"></a>CHtmlView::OnStatusTextChange  
 このメンバー関数は、WebBrowser コントロールに関連付けられたステータス バーのテキストが変更されたことをアプリケーションに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnStatusTextChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 新しいステータス バーのテキストを含む文字列です。  
  
##  <a name="ontheatermode"></a>CHtmlView::OnTheaterMode  
 このメンバー関数がフレームワークによって呼び出されるときに、 [TheaterMode](https://msdn.microsoft.com/library/aa768273.aspx)プロパティが変更されました。  
  
```  
virtual void OnTheaterMode(BOOL bTheaterMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *bTheaterMode*  
 Internet Explorer がシアター モードである場合は&0; 以外それ以外の場合はゼロ。  
  
##  <a name="ontitlechange"></a>CHtmlView::OnTitleChange  
 このメンバー関数は、WebBrowser コントロール内のドキュメントのタイトルは、アプリケーションに通知するためにフレームワークまたは変更によって呼び出されます。  
  
```  
virtual void OnTitleChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 新しいドキュメント タイトルです。  
  
### <a name="remarks"></a>コメント  
 HTML のタイトルを変更する可能性があります。HTML がダウンロードも中にドキュメントの URL は、タイトルとして設定されます。 実際のタイトル (存在する場合) は、HTML から解析された、実際のタイトルを反映するように、タイトルが変更されます。  
  
##  <a name="ontoolbar"></a>CHtmlView::OnToolBar  
 このメンバー関数がフレームワークによって呼び出されますときに、[ツールバー](https://msdn.microsoft.com/library/aa768274.aspx)プロパティが変更されました。  
  
```  
virtual void OnToolBar(BOOL bToolBar);
```  
  
### <a name="parameters"></a>パラメーター  
 *bToolBar*  
 Internet Explorer のツールバーが表示されている場合は&0; 以外。 それ以外の場合は&0; またはです。  
  
##  <a name="ontranslateaccelerator"></a>CHtmlView::OnTranslateAccelerator  
 Internet Explorer または MSHTML により呼び出されるときに[IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360)または[IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756)コンテナーのメッセージ キューからのメニューのアクセラレータ キー メッセージを処理します。  
  
```  
virtual HRESULT OnTranslateAccelerator(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMsg`  
 変換する必要があるメッセージへのポインター。  
  
 `pguidCmdGroup`  
 コマンド グループの識別子です。  
  
 `nCmdID`  
 コマンド id。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、または**S_FALSE**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnTranslateAccelerator`に対応するため、 `TranslateAccelerator` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="ontranslateurl"></a>CHtmlView::OnTranslateUrl  
 読み込む URL をホストが変更できるようにするため、Internet Explorer または MSHTML によって呼び出されます。  
  
```  
virtual HRESULT OnTranslateUrl(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwTranslate`  
 将来使用するために予約されています。  
  
 `pchURLIn`  
 Internet Explorer または変換する URL を表す MSHTML によって指定された文字列のアドレスです。  
  
 `ppchURLOut`  
 変換された URL のアドレスを受け取る文字列ポインターのアドレスです。 ホストは、タスク メモリ アロケーターを使用するバッファーを割り当てます。 このパラメーターの内容は、必ずに初期化する**NULL**URL が変換されないか、メソッドが失敗した場合でも、します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`URL が変換された場合**S_FALSE** URL が変換されていない場合や、エラーが発生した場合の OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`OnTranslateUrl`に対応するため、 `TranslateUrl` Microsoft の Web ブラウザー コントロールから通知されます。 参照してください[IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
##  <a name="onupdateui"></a>CHtmlView::OnUpdateUI  
 コマンドの状態が変化したことをホストに通知します。  
  
```  
virtual HRESULT OnUpdateUI();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、それ以外の場合は OLE 定義のエラー コード。  
  
### <a name="remarks"></a>コメント  
 ホストは、ツール バー ボタンの状態を更新する必要があります。 このメソッドはからの戻り値に関係なく`ShowUI`です。 オーバーライド`OnUpdateUI`に対応するため、 `UpdateUI` Microsoft の Web ブラウザー コントロールから通知されます。  
  
##  <a name="onvisible"></a>CHtmlView::OnVisible  
 このメンバー関数が呼び出されますフレームワークによって、web ブラウザーのウィンドウを表示または非表示する必要があります。  
  
```  
virtual void OnVisible(BOOL bVisible);
```  
  
### <a name="parameters"></a>パラメーター  
 `bVisible`  
 オブジェクトが表示されている場合は&0; 以外。 それ以外の場合は&0; またはです。  
  
### <a name="remarks"></a>コメント  
 これにより、Internet Explorer ウィンドウの動作は同じように動作するオブジェクトのコントロール ホスト ウィンドウです。  
  
##  <a name="putproperty"></a>CHtmlView::PutProperty  
 指定したオブジェクトに関連付けられているプロパティを設定するには、このメンバー関数を呼び出します。  
  
```  
void PutProperty(
    LPCTSTR lpszProperty,  
    const VARIANT& vtValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    double dValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    long lValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    LPCTSTR lpszValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    short nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProperty`  
 設定するプロパティを含む文字列。  
  
 *vtValue*  
 示されたプロパティの新しい値`lpszProperty`です。  
  
 *lpszPropertyName*  
 設定するプロパティの名前を含む文字列へのポインター。  
  
 *dValue*  
 プロパティの新しい値。  
  
 `lValue`  
 プロパティの新しい値。  
  
 `lpszValue`  
 プロパティの新しい値を含む文字列へのポインター。  
  
 `nValue`  
 プロパティの新しい値。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="queryformscommand"></a>CHtmlView::QueryFormsCommand  
 ユーザー インターフェイスのイベントによって生成された&1; つ以上のコマンドの状態を調べるためにクエリを実行します。  
  
```  
HRESULT QueryFormsCommand(
    DWORD dwCommandID,  
    BOOL* pbSupported,  
    BOOL* pbEnabled,  
    BOOL* pbChecked);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCommandID`  
 照会するコマンドの識別子です。  
  
 *pbSupported*  
 ポインター、 **BOOL**を指定する場合のコマンドは、(で識別される`dwCommandID`) はサポートされています。 TRUE の場合、このコマンドはサポートされています。それ以外の場合は FALSE。  
  
 `pbEnabled`  
 ポインター、 **BOOL**を指定する場合のコマンドは、(で識別される`dwCommandID`) が有効になっています。 TRUE の場合、このコマンドはサポートされています。それ以外の場合は FALSE。  
  
 *pbChecked*  
 ポインター、 **BOOL**を指定する場合のコマンドは、(で識別される`dwCommandID`) がオンになっています。 TRUE の場合、このコマンドはサポートされています。それ以外の場合は FALSE。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。 使用可能な値の完全な一覧については、次を参照してください。 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 `QueryFormsCommand`動作を実装、 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491)メソッドです。  
  
##  <a name="querystatuswb"></a>CHtmlView::QueryStatusWB  
 コマンド ステータスを照会するには、このメンバー関数を呼び出します。  
  
```  
OLECMDF QueryStatusWB(OLECMDID cmdID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 [OLECMDID](http://msdn.microsoft.com/library/windows/desktop/ms691264)呼び出し元が状態情報を必要コマンドの値。  
  
### <a name="return-value"></a>戻り値  
 アドレス、 [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237)コマンドのステータスを受信した値です。  
  
### <a name="remarks"></a>コメント  
 `QueryStatusWB`動作を実装、 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491)メソッドです。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="refresh"></a>CHtmlView::Refresh  
 URL または web ブラウザーが現在表示されているファイルを再読み込みします。  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>コメント  
 **更新**更新のレベルを設定するためのパラメーターが含まれていません。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="refresh2"></a>CHtmlView::Refresh2  
 Internet Explorer が現在表示されているファイルを再読み込みします。  
  
```  
void Refresh2(int nLevel);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLevel`  
 更新レベルを指定する変数のアドレス。 可能な変数が定義されている[RefreshConstants](https://msdn.microsoft.com/library/aa768363.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 異なり[更新](#refresh)、`Refresh2`更新のレベルを指定するパラメーターが含まれています。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="setaddressbar"></a>CHtmlView::SetAddressBar  
 Internet Explorer オブジェクトのアドレス バーを非表示には、このメンバー関数を呼び出します。  
  
```  
void SetAddressBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 アドレス バーを表示する&0; 以外の値それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer に適用されます。 WebBrowser コントロールでこの呼び出しを使用する場合に返されません、エラーが、この呼び出しは無視されます。  
  
##  <a name="setfullscreen"></a>CHtmlView::SetFullScreen  
 Internet Explorer を全画面表示か、通常のウィンドウのいずれかのモードに設定するには、このメンバー関数を呼び出します。  
  
```  
void SetFullScreen(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 全画面表示モードのそれ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 全画面表示モードでは、Internet Explorer のメイン ウィンドウを最大化し、ステータス バー、ツールバー、メニュー バー、およびタイトル バーを非表示します。  
  
 Internet Explorer に適用されます。 WebBrowser コントロールでこの呼び出しを使用する場合に返されません、エラーが、この呼び出しは無視されます。  
  
##  <a name="setheight"></a>CHtmlView::SetHeight  
 Internet Explorer のメイン ウィンドウの高さを設定するには、このメンバー関数を呼び出します。  
  
```  
void SetHeight(long nNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewValue`  
 メイン ウィンドウのピクセル単位の高さ。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="setleft"></a>CHtmlView::SetLeft  
 Internet Explorer のメイン ウィンドウの水平方向の位置を設定します。  
  
```  
void SetLeft(long nNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewValue`  
 メイン ウィンドウの左端の画面座標。  
  
##  <a name="setmenubar"></a>CHtmlView::SetMenuBar  
 Internet Explorer のメニュー バーを非表示には、このメンバー関数を呼び出します。  
  
```  
void SetMenuBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 メニュー バーを表示する&0; 以外の値それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer に適用されます。 WebBrowser コントロールでこの呼び出しを使用する場合に返されません、エラーが、この呼び出しは無視されます。  
  
##  <a name="setoffline"></a>CHtmlView::SetOffline  
 WebBrowser コントロールが現在オフライン モードで動作しているかどうかを示す値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetOffline(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 ローカル キャッシュから読み取るには&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 オフライン モードでは、ブラウザーは、ソース ドキュメントではなくローカル キャッシュからの HTML ページを読み取ります。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="setregisterasbrowser"></a>CHtmlView::SetRegisterAsBrowser  
 ターゲットの名前解決のための最上位レベルのブラウザーとして WebBrowser コントロールを登録するかどうかを示す値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetRegisterAsBrowser(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 最上位レベルのブラウザーとして Internet Explorer が登録されているかどうかを決定します。 Web ブラウザーが最上位レベルのブラウザーとして登録されている&0; 以外の場合0 の場合、最上位レベルのブラウザーではありません。 既定値は&0; です。  
  
### <a name="remarks"></a>コメント  
 最上位レベルのブラウザーは、ブラウザーを既定のブラウザーとしてレジストリに設定します。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="setregisterasdroptarget"></a>CHtmlView::SetRegisterAsDropTarget  
 ナビゲーションのドロップ先として、WebBrowser コントロールを登録するかどうかを示す値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetRegisterAsDropTarget(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 WebBrowser コントロールがナビゲーションのドロップ先として登録されているかどうかを判断します。 オブジェクトがドロップ ターゲットとして登録されている&0; 以外の場合0 の場合、ドロップ先ではありません。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="setsilent"></a>CHtmlView::SetSilent  
 すべてのダイアログ ボックスが表示されるかどうかを示す値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetSilent(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 ゼロ以外の場合、ダイアログ ボックスは表示されません。0 の場合、ダイアログ ボックスが表示されます。 既定値は&0; です。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="setstatusbar"></a>CHtmlView::SetStatusBar  
 ステータス バーを表示するには、このメンバー関数を呼び出します。  
  
```  
void SetStatusBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 ステータス バーを表示する場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer に適用されます。 WebBrowser コントロールでこの呼び出しを使用する場合に返されません、エラーが、この呼び出しは無視されます。  
  
##  <a name="settheatermode"></a>CHtmlView::SetTheaterMode  
 WebBrowser コントロールがシアター モードかどうかを示す値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetTheaterMode(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 WebBrowser コントロールをシアター モードに設定するのには&0; 以外。それ以外の場合&0; を返します。 既定値は&0; です。  
  
### <a name="remarks"></a>コメント  
 シアター モードで web ブラウザーがある場合は、ブラウザーのメイン ウィンドウが画面全体を占めるおよびナビゲーション ツールの最小限のセットを含むツールバーが表示されたら、画面の右上隅のステータス バーが表示されます。  
  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="settoolbar"></a>CHtmlView::SetToolBar  
 Internet Explorer のツールバーを非表示には、このメンバー関数を呼び出します。  
  
```  
void SetToolBar(int nNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewValue`  
 ツールバーを表示するかどうかを示します。 ツールバーを表示する場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer に適用されます。 WebBrowser コントロールでこの呼び出しを使用する場合に返されません、エラーが、この呼び出しは無視されます。  
  
##  <a name="settop"></a>CHtmlView::SetTop  
 WebBrowser コントロールの内側の上端とコンテナーの上端の間の距離を設定するには、このメンバー関数を呼び出す  
  
```  
void SetTop(long nNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewValue`  
 メイン ウィンドウの上端の画面座標。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="setvisible"></a>CHtmlView::SetVisible  
 WebBrowser コントロールの可視性の状態を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetVisible(BOOL bNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNewValue`  
 コントロールが表示されている場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
##  <a name="setwidth"></a>CHtmlView::SetWidth  
 Internet Explorer のメイン ウィンドウの幅を設定します。  
  
```  
void SetWidth(long nNewValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewValue`  
 Internet Explorer のメイン ウィンドウのピクセル単位の幅。  
  
##  <a name="stop"></a>CHtmlView::Stop  
 保留中のナビゲーションをキャンセルまたは操作をダウンロードし、バック グラウンド サウンドやアニメーションなど、動的なページ要素をすべてを停止するには、このメンバー関数を呼び出します。  
  
```  
void Stop();
```  
  
### <a name="remarks"></a>コメント  
 Internet Explorer と WebBrowser に適用されます。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCIE](../../visual-cpp-samples.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)


