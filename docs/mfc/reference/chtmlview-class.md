---
title: "CHtmlView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブラウザー、MFC サポート"
  - "CHtmlView クラス"
  - "WebBrowser コントロール"
  - "WebBrowser コントロール、MFC サポート"
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC のドキュメント\/ビュー アーキテクチャのコンテキストで WebBrowser コントロールの機能を提供します。  
  
## 構文  
  
```  
class CHtmlView : public CFormView  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHtmlView::Create](../Topic/CHtmlView::Create.md)|WebBrowser コントロールを作成します。|  
|[CHtmlView::CreateControlSite](../Topic/CHtmlView::CreateControlSite.md)|フォーム上のコントロールをホストするコントロール サイトのインスタンスを作成するために使用する、オーバーライド可能なメソッド。|  
|[CHtmlView::ExecFormsCommand](../Topic/CHtmlView::ExecFormsCommand.md)|指定されたコマンドを `IOleCommandTarget::Exec` メソッドを使用して実行します。|  
|[CHtmlView::ExecWB](../Topic/CHtmlView::ExecWB.md)|コマンドを実行します。|  
|[CHtmlView::GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)|Internet Explorer オブジェクトのアドレス バーが表示されるかどうかを判別します。 \(WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。\)|  
|[CHtmlView::GetApplication](../Topic/CHtmlView::GetApplication.md)|Internet Explorer アプリケーションの現在のインスタンスを含むアプリケーションを表すアプリケーション オブジェクトを取得します。|  
|[CHtmlView::GetBusy](../Topic/CHtmlView::GetBusy.md)|ダウンロードやその他のアクティビティが進行中かどうかを示す値を取得します。|  
|[CHtmlView::GetContainer](../Topic/CHtmlView::GetContainer.md)|WebBrowser コントロールのコンテナーを取得します。|  
|[CHtmlView::GetFullName](../Topic/CHtmlView::GetFullName.md)|Web ブラウザーに表示されるリソースのフル ネームを、パスも含めて取得します。 \(WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。\)|  
|[CHtmlView::GetFullScreen](../Topic/CHtmlView::GetFullScreen.md)|WebBrowser コントロールが全画面表示モードと標準ウィンドウ モードのどちらで動作しているかを示します。|  
|[CHtmlView::GetHeight](../Topic/CHtmlView::GetHeight.md)|Internet Explorer のメイン ウィンドウの高さを取得します。|  
|[CHtmlView::GetHtmlDocument](../Topic/CHtmlView::GetHtmlDocument.md)|アクティブな HTML ドキュメントを取得します。|  
|[CHtmlView::GetLeft](../Topic/CHtmlView::GetLeft.md)|Internet Explorer のメイン ウィンドウの左端の画面座標を取得します。|  
|[CHtmlView::GetLocationName](../Topic/CHtmlView::GetLocationName.md)|WebBrowser が現在表示しているリソースの名前を取得します。|  
|[CHtmlView::GetLocationURL](../Topic/CHtmlView::GetLocationURL.md)|WebBrowser が現在表示しているリソースの URL を取得します。|  
|[CHtmlView::GetMenuBar](../Topic/CHtmlView::GetMenuBar.md)|メニュー バーが表示されるかどうかを判別する値を取得します。|  
|[CHtmlView::GetOffline](../Topic/CHtmlView::GetOffline.md)|コントロールがオフラインかどうかを判別する値を取得します。|  
|[CHtmlView::GetParentBrowser](../Topic/CHtmlView::GetParentBrowser.md)|`IDispatch` インターフェイスへのポインターを取得します。 詳細については、「[Implementing the IDispatch Interface](http://msdn.microsoft.com/ja-jp/0e171f7f-0022-4e9b-ac8e-98192828e945)」を参照してください。|  
|[CHtmlView::GetProperty](../Topic/CHtmlView::GetProperty.md)|指定したオブジェクトに関連付けられているプロパティの現在の値を取得します。|  
|[CHtmlView::GetReadyState](../Topic/CHtmlView::GetReadyState.md)|Web ブラウザーのオブジェクトの準備完了状態を取得します。|  
|[CHtmlView::GetRegisterAsBrowser](../Topic/CHtmlView::GetRegisterAsBrowser.md)|WebBrowser コントロールがターゲット名解決の最上位レベルのブラウザーとして登録されているかどうかを示します。|  
|[CHtmlView::GetRegisterAsDropTarget](../Topic/CHtmlView::GetRegisterAsDropTarget.md)|WebBrowser コントロールがナビゲーションのドロップ先として登録されているかどうかを示します。|  
|[CHtmlView::GetSilent](../Topic/CHtmlView::GetSilent.md)|ダイアログ ボックスを表示できるかどうかを示します。|  
|[CHtmlView::GetSource](../Topic/CHtmlView::GetSource.md)|Web ページの HTML ソース コード。|  
|[CHtmlView::GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)|Internet Explorer のステータス バーが表示されているかどうかを示します。 \(WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。\)|  
|[CHtmlView::GetTheaterMode](../Topic/CHtmlView::GetTheaterMode.md)|WebBrowser コントロールがシアター モードかどうかを示します。|  
|[CHtmlView::GetToolBar](../Topic/CHtmlView::GetToolBar.md)|ツール バーが表示されているかどうかを判別する値を取得します。|  
|[CHtmlView::GetTop](../Topic/CHtmlView::GetTop.md)|Internet Explorer のメイン ウィンドウの上端の画面座標を取得します。|  
|[CHtmlView::GetTopLevelContainer](../Topic/CHtmlView::GetTopLevelContainer.md)|現在のオブジェクトが WebBrowser コントロールの最上位のコンテナーかどうかを示す値を取得します。|  
|[CHtmlView::GetType](../Topic/CHtmlView::GetType.md)|ドキュメント オブジェクトの型名を取得します。|  
|[CHtmlView::GetVisible](../Topic/CHtmlView::GetVisible.md)|オブジェクトの表示または非表示を示す値を取得します。|  
|[CHtmlView::GetWidth](../Topic/CHtmlView::GetWidth.md)|Internet Explorer のメイン ウィンドウの幅を取得します。|  
|[CHtmlView::GoBack](../Topic/CHtmlView::GoBack.md)|履歴の一覧の前の項目に移動します。|  
|[CHtmlView::GoForward](../Topic/CHtmlView::GoForward.md)|履歴の一覧の次の項目に移動します。|  
|[CHtmlView::GoHome](../Topic/CHtmlView::GoHome.md)|現在のホーム ページまたはスタート ページに移動します。|  
|[CHtmlView::GoSearch](../Topic/CHtmlView::GoSearch.md)|現在の検索ページに移動します。|  
|[CHtmlView::LoadFromResource](../Topic/CHtmlView::LoadFromResource.md)|WebBrowser コントロールのリソースを読み込みます。|  
|[CHtmlView::Navigate](../Topic/CHtmlView::Navigate.md)|URL で識別されるリソースに移動します。|  
|[CHtmlView::Navigate2](../Topic/CHtmlView::Navigate2.md)|URL で識別されるリソースまたは完全なパスで識別されるファイルに移動します。|  
|[CHtmlView::OnBeforeNavigate2](../Topic/CHtmlView::OnBeforeNavigate2.md)|指定された WebBrowser 内での移動 \(ウィンドウかフレームセット要素上で\) が起こる前に呼び出されます。|  
|[CHtmlView::OnCommandStateChange](../Topic/CHtmlView::OnCommandStateChange.md)|Web ブラウザー コマンドの有効な状態が変更されたことをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnDocumentComplete](../Topic/CHtmlView::OnDocumentComplete.md)|ドキュメントが `READYSTATE_COMPLETE` 状態に達していることをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnDocWindowActivate](../Topic/CHtmlView::OnDocWindowActivate.md)|コンテナーのドキュメント ウィンドウがアクティブ化または非アクティブ化されたときにアクティブなインプレース オブジェクトに通知する、[IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281) の Internet Explorer または MSHTML の実装から呼び出されます。|  
|[CHtmlView::OnDownloadBegin](../Topic/CHtmlView::OnDownloadBegin.md)|ナビゲーション操作が開始中であることをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnDownloadComplete](../Topic/CHtmlView::OnDownloadComplete.md)|ナビゲーション操作が終了したとき、中止したとき、または失敗したときに呼び出されます。|  
|[CHtmlView::OnEnableModeless](../Topic/CHtmlView::OnEnableModeless.md)|コンテナーがモーダル ダイアログ ボックスを作成または破棄するときに、モードレス ダイアログ ボックスを有効または無効にするために呼び出されます。|  
|[CHtmlView::OnFilterDataObject](../Topic/CHtmlView::OnFilterDataObject.md)|ホストが Internet Explorer または MSHTML のデータ オブジェクトを置き換えできるように Internet Explorer または MSHTML によってホスト上で呼び出されます。|  
|[CHtmlView::OnFrameWindowActivate](../Topic/CHtmlView::OnFrameWindowActivate.md)|コンテナーの最上位レベルのフレーム ウィンドウがアクティブ化または非アクティブ化されたときに、オブジェクトに通知するために [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) から呼び出されます。|  
|[CHtmlView::OnFullScreen](../Topic/CHtmlView::OnFullScreen.md)|FullScreen プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnGetDropTarget](../Topic/CHtmlView::OnGetDropTarget.md)|ドロップのターゲットとして使用されている Internet Explorer または MSHTML によって呼び出され、ホストが代わりの [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) を提供できるようにします。|  
|[CHtmlView::OnGetExternal](../Topic/CHtmlView::OnGetExternal.md)|ホストの `IDispatch` インターフェイスを取得するために Internet Explorer または MSHTML によって呼び出されます。|  
|[CHtmlView::OnGetHostInfo](../Topic/CHtmlView::OnGetHostInfo.md)|Internet Explorer または MSHTML ホストの UI 機能を取得します。|  
|[CHtmlView::OnGetOptionKeyPath](../Topic/CHtmlView::OnGetOptionKeyPath.md)|Internet Explorer または MSHTML がユーザーの設定を格納しているレジストリ キーを返します。|  
|[CHtmlView::OnHideUI](../Topic/CHtmlView::OnHideUI.md)|Internet Explorer または MSHTML がメニューやツール バーを削除するときに呼び出されます。|  
|[CHtmlView::OnMenuBar](../Topic/CHtmlView::OnMenuBar.md)|MenuBar プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnNavigateComplete2](../Topic/CHtmlView::OnNavigateComplete2.md)|ハイパーリンクへの移動 \(ウィンドウかフレームセット要素上で\) が終了した後で呼び出されます。|  
|[CHtmlView::OnNavigateError](../Topic/CHtmlView::OnNavigateError.md)|ハイパーリンクへの移動が失敗したときに、フレームワークによって呼び出されます。|  
|[CHtmlView::OnNewWindow2](../Topic/CHtmlView::OnNewWindow2.md)|リソースを表示する新しいウィンドウが作成されるときに呼び出されます。|  
|[CHtmlView::OnProgressChange](../Topic/CHtmlView::OnProgressChange.md)|ダウンロード操作の進行が更新されたことをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnPropertyChange](../Topic/CHtmlView::OnPropertyChange.md)|[PutProperty](../Topic/CHtmlView::PutProperty.md) メソッドがプロパティ値を変更したことをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnQuit](../Topic/CHtmlView::OnQuit.md)|Internet Explorer アプリケーションが終了しそうなときに、アプリケーションに通知するために呼び出されます。 \(Internet Explorer のみに適用\)|  
|[CHtmlView::OnResizeBorder](../Topic/CHtmlView::OnResizeBorder.md)|境界領域のサイズを変更する必要があることをオブジェクトに警告する、[IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053) のInternet Explorer または MSHTML の実装から呼び出されます。|  
|[CHtmlView::OnShowContextMenu](../Topic/CHtmlView::OnShowContextMenu.md)|コンテキスト メニューを表示しようとしているときに、Internet Explorer または MSHTML から呼び出されます。|  
|[CHtmlView::OnShowUI](../Topic/CHtmlView::OnShowUI.md)|Internet Explorer または MSHTML がメニューやツール バーを表示する前に呼び出されます。|  
|[CHtmlView::OnStatusBar](../Topic/CHtmlView::OnStatusBar.md)|StatusBar プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnStatusTextChange](../Topic/CHtmlView::OnStatusTextChange.md)|WebBrowser コントロールと関連付けられているステータス バーのテキストが変更されたことをアプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnTheaterMode](../Topic/CHtmlView::OnTheaterMode.md)|TheaterMode プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnTitleChange](../Topic/CHtmlView::OnTitleChange.md)|WebBrowser コントロールのドキュメントのタイトルが使用できるようになるかどうか、また変更するかどうかを、アプリケーションに通知するために呼び出されます。|  
|[CHtmlView::OnToolBar](../Topic/CHtmlView::OnToolBar.md)|ToolBar プロパティが変化したときに呼び出されます。|  
|[CHtmlView::OnTranslateAccelerator](../Topic/CHtmlView::OnTranslateAccelerator.md)|[IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) または [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) が呼び出され、コンテナーのメッセージ キューからのメニュー アクセス キーのメッセージを処理するときに、Internet Explorer または MSHTML によって呼び出されます。|  
|[CHtmlView::OnTranslateUrl](../Topic/CHtmlView::OnTranslateUrl.md)|読み込む URL をホストが変更できるようにするため、Internet Explorer または MSHTML によって呼び出されます。|  
|[CHtmlView::OnUpdateUI](../Topic/CHtmlView::OnUpdateUI.md)|コマンドの状態が変化したことをホストに通知します。|  
|[CHtmlView::OnVisible](../Topic/CHtmlView::OnVisible.md)|WebBrowser コントロールのウィンドウが表示または隠す状態になるべきときに呼び出されます。|  
|[CHtmlView::PutProperty](../Topic/CHtmlView::PutProperty.md)|指定したオブジェクトに関連付けられているプロパティの値を設定します。|  
|[CHtmlView::QueryFormsCommand](../Topic/CHtmlView::QueryFormsCommand.md)|ユーザー インターフェイスのイベントによって生成された 1 つ以上のコマンドの状態を調べるためにクエリを実行します。|  
|[CHtmlView::QueryStatusWB](../Topic/CHtmlView::QueryStatusWB.md)|WebBrowser コントロールによって処理されているコマンドの状態を調べるためにクエリを実行します。|  
|[CHtmlView::Refresh](../Topic/CHtmlView::Refresh.md)|現在のファイルを再読み込みします。|  
|[CHtmlView::Refresh2](../Topic/CHtmlView::Refresh2.md)|現在のファイルを再読み込みし、必要に応じて `pragma:nocache` ヘッダーが送信されないようにします。|  
|[CHtmlView::SetAddressBar](../Topic/CHtmlView::SetAddressBar.md)|Internet Explorer のオブジェクトのアドレス バーを表示または非表示にします。 \(WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。\)|  
|[CHtmlView::SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)|コントロールが全画面表示モードと標準ウィンドウ モードのどちらで動作するかを決定する値を設定します。 \(WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。\)|  
|[CHtmlView::SetHeight](../Topic/CHtmlView::SetHeight.md)|Internet Explorer のメイン ウィンドウの高さを設定します。|  
|[CHtmlView::SetLeft](../Topic/CHtmlView::SetLeft.md)|Internet Explorer のメイン ウィンドウの水平方向の位置を設定します。|  
|[CHtmlView::SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)|コントロールのメニュー バーを表示するかどうかを決定する値を設定します。 \(WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。\)|  
|[CHtmlView::SetOffline](../Topic/CHtmlView::SetOffline.md)|コントロールがオフラインであるかどうかを決定する値を設定します。|  
|[CHtmlView::SetRegisterAsBrowser](../Topic/CHtmlView::SetRegisterAsBrowser.md)|WebBrowser コントロールがターゲット名解決の最上位レベルのブラウザーとして登録されているかどうかを示す値を設定します。|  
|[CHtmlView::SetRegisterAsDropTarget](../Topic/CHtmlView::SetRegisterAsDropTarget.md)|WebBrowser コントロールがナビゲーションのドロップ先として登録されているかどうかを示す値を設定します。|  
|[CHtmlView::SetSilent](../Topic/CHtmlView::SetSilent.md)|コントロールがダイアログ ボックスを表示するかどうかを決定する値を設定します。|  
|[CHtmlView::SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)|Internet Explorer のステータス バーを表示するかどうかを決定する値を設定します。 \(WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。\)|  
|[CHtmlView::SetTheaterMode](../Topic/CHtmlView::SetTheaterMode.md)|WebBrowser コントロールがシアター モードかどうかを示す値を設定します。|  
|[CHtmlView::SetToolBar](../Topic/CHtmlView::SetToolBar.md)|コントロールのツール バーを表示するかどうかを決定する値を設定します。 \(WebBrowser コントロールでは無視されます。Internet Explorer の場合のみです。\)|  
|[CHtmlView::SetTop](../Topic/CHtmlView::SetTop.md)|Internet Explorer のメイン ウィンドウの水平方向の位置を設定します。|  
|[CHtmlView::SetVisible](../Topic/CHtmlView::SetVisible.md)|オブジェクトの表示または非表示を示す値を設定します。|  
|[CHtmlView::SetWidth](../Topic/CHtmlView::SetWidth.md)|Internet Explorer のメイン ウィンドウの幅を設定します。|  
|[CHtmlView::Stop](../Topic/CHtmlView::Stop.md)|ファイルを開くことを中止します。|  
  
## 解説  
 WebBrowser コントロールは、World Wide Web 上のサイト、およびローカル ファイル システム内とネットワーク上のフォルダーをユーザーが閲覧できるウィンドウです。 WebBrowser コントロールは、ハイパーリンクと Uniform Resource Locator \(URL\) のナビゲーションをサポートし、履歴一覧を管理します。  
  
## MFC アプリケーションで CHtmlView クラスを使用する  
 標準の MFC フレームワーク アプリケーション \(SDI または MDI ベースのいずれか\) では、通常、ビュー オブジェクトは特殊化された一連のクラスから派生します。 これらのクラスはすべて `CView` から派生したものであり、`CView` によって提供される範囲を超えて特殊機能を提供します。  
  
 `CHtmlView` 上のアプリケーションのビュー クラスに基づいて、ビューに WebBrowser コントロールを提供します。 これにより、アプリケーションを効率的に Web ブラウザーにできます。 Web ブラウザー スタイルのアプリケーションを作成する場合は、MFC アプリケーション ウィザードを使用して、`CHtmlView` をビュー クラスとして指定する方法をお勧めします。 MFC アプリケーション内で WebBrowser コントロールを実装して使用する方法について詳しくは、「[Web ブラウザー スタイルのアプリケーションを作成する](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)」をご覧ください。  
  
> [!NOTE]
>  WebBrowser ActiveX コントロール \(および `CHtmlView`\) は、Internet Explorer 4.0 以降がインストールされている Windows NT Version 4.0 以降で実行されるプログラムでのみ使用できます。  
  
 `CHtmlView` は Web \(および\/または HTML ドキュメント\) にアクセスするアプリケーション用に設計されています。 次の `CHtmlView` メンバー関数は、Internet Explorer のアプリケーションのみに適用されます。 これらの関数は WebBrowser コントロールで成功しますが、視覚的は変化はありません。  
  
-   [GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)  
  
-   [GetFullName](../Topic/CHtmlView::GetFullName.md)  
  
-   [GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)  
  
-   [SetAddressBar](../Topic/CHtmlView::SetAddressBar.md)  
  
-   [SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)  
  
-   [SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)  
  
-   [SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)  
  
-   [SetToolBar](../Topic/CHtmlView::SetToolBar.md)  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## 必要条件  
 **ヘッダー:** afxhtml.h  
  
## 参照  
 [MFC サンプル MFCIE](../../top/visual-cpp-samples.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx)