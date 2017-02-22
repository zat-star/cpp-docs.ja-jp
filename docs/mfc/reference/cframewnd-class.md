---
title: "CFrameWnd クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWnd クラス"
  - "フレーム ウィンドウ クラス, 基本クラス"
  - "フレーム ウィンドウ, 作成"
  - "シングル ドキュメント インターフェイス (SDI), フレーム ウィンドウ"
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CFrameWnd クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ウィンドウを管理するメンバーと共に、Windows のシングル ドキュメント インターフェイス \(SDI: Single Document Interface\) のオーバーラップ フレーム ウィンドウまたはポップアップ フレーム ウィンドウの機能を提供します。  
  
## 構文  
  
```  
class CFrameWnd : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFrameWnd::CFrameWnd](../Topic/CFrameWnd::CFrameWnd.md)|`CFrameWnd` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFrameWnd::ActivateFrame](../Topic/CFrameWnd::ActivateFrame.md)|フレームを表示し、ユーザーが使えるようにします。|  
|[CFrameWnd::BeginModalState](../Topic/CFrameWnd::BeginModalState.md)|フレーム ウィンドウをモーダルに設定します。|  
|[CFrameWnd::Create](../Topic/CFrameWnd::Create.md)|`CFrameWnd` オブジェクトに関連付けられた Windows のフレーム ウィンドウを作成し、初期化します。|  
|[CFrameWnd::CreateView](../Topic/CFrameWnd::CreateView.md)|フレーム内に `CView` から派生されていないビューを作成します。|  
|[CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md)|コントロール バーをドッキングします。|  
|[CFrameWnd::EnableDocking](../Topic/CFrameWnd::EnableDocking.md)|コントロール バーをドッキングできるようにします。|  
|[CFrameWnd::EndModalState](../Topic/CFrameWnd::EndModalState.md)|フレーム ウィンドウのモーダル状態を終了します。  `BeginModalState` で無効にされていたすべてのウィンドウを有効にします。|  
|[CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md)|コントロール バーをフローティングにします。|  
|[CFrameWnd::GetActiveDocument](../Topic/CFrameWnd::GetActiveDocument.md)|アクティブな **CDocument** オブジェクトを返します。|  
|[CFrameWnd::GetActiveFrame](../Topic/CFrameWnd::GetActiveFrame.md)|アクティブな `CFrameWnd` オブジェクトを返します。|  
|[CFrameWnd::GetActiveView](../Topic/CFrameWnd::GetActiveView.md)|アクティブな `CView` オブジェクトを返します。|  
|[CFrameWnd::GetControlBar](../Topic/CFrameWnd::GetControlBar.md)|コントロール バーを取得します。|  
|[CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md)|フレーム ウィンドウのドッキング状態を取得します。|  
|[CFrameWnd::GetMenuBarState](../Topic/CFrameWnd::GetMenuBarState.md)|現在の MFC アプリケーションのメニューの表示状態を取得します。|  
|[CFrameWnd::GetMenuBarVisibility](../Topic/CFrameWnd::GetMenuBarVisibility.md)|現在の MFC アプリケーションのメニューの既定の動作が非表示にしたり、表示されるかどうかを示します。|  
|[CFrameWnd::GetMessageBar](../Topic/CFrameWnd::GetMessageBar.md)|フレーム ウィンドウにのステータス バーにポインターを返します。|  
|[CFrameWnd::GetMessageString](../Topic/CFrameWnd::GetMessageString.md)|コマンド ID に対応するメッセージを取得します。|  
|[CFrameWnd::GetTitle](../Topic/CFrameWnd::GetTitle.md)|関連するコントロール バーのタイトルを取得します。|  
|[CFrameWnd::InitialUpdateFrame](../Topic/CFrameWnd::InitialUpdateFrame.md)|フレーム ウィンドウのすべてのビューが `OnInitialUpdate` メンバー関数から呼ばれるようになります。|  
|[CFrameWnd::InModalState](../Topic/CFrameWnd::InModalState.md)|フレーム ウィンドウがモーダル状態かどうかを示す値を返します。|  
|[CFrameWnd::IsTracking](../Topic/CFrameWnd::IsTracking.md)|現在、分割バーが動いているかを取得します。|  
|[CFrameWnd::LoadAccelTable](../Topic/CFrameWnd::LoadAccelTable.md)|アクセラレータ テーブルを読み込みます。|  
|[CFrameWnd::LoadBarState](../Topic/CFrameWnd::LoadBarState.md)|コントロール バーの設定を元に戻します。|  
|[CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)|リソース情報から動的にフレーム ウィンドウを作成します。|  
|[CFrameWnd::NegotiateBorderSpace](../Topic/CFrameWnd::NegotiateBorderSpace.md)|フレーム ウィンドウの境界領域を調整します。|  
|[CFrameWnd::OnBarCheck](../Topic/CFrameWnd::OnBarCheck.md)|指定されたコントロール バーでアクションを実行するたびに呼び出されます。|  
|[CFrameWnd::OnContextHelp](../Topic/CFrameWnd::OnContextHelp.md)|埋め込み先アイテムに対する Shift \+ F1 ヘルプを処理します。|  
|[CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md)|アプリケーションのメイン フレーム ウィンドウを印刷プレビュー モードにしたり、元に戻したりします。|  
|[CFrameWnd::OnUpdateControlBarMenu](../Topic/CFrameWnd::OnUpdateControlBarMenu.md)|関連するメニューが更新されたときに、フレームワークによって呼び出されます。|  
|[CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md)|`CFrameWnd` オブジェクトのコントロール バーを再配置します。|  
|[CFrameWnd::SaveBarState](../Topic/CFrameWnd::SaveBarState.md)|コントロール バーの設定を保存します。|  
|[CFrameWnd::SetActivePreviewView](../Topic/CFrameWnd::SetActivePreviewView.md)|指定されたビューをリッチ プレビュー用のアクティブなビューとして指定します。|  
|[CFrameWnd::SetActiveView](../Topic/CFrameWnd::SetActiveView.md)|アクティブな `CView` オブジェクトを設定します。|  
|[CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md)|フレーム ウィンドウをメイン ウィンドウにドッキングします。|  
|[CFrameWnd::SetMenuBarState](../Topic/CFrameWnd::SetMenuBarState.md)|現在の MFC アプリケーションのメニューの表示状態を非表示または表示に設定します。|  
|[CFrameWnd::SetMenuBarVisibility](../Topic/CFrameWnd::SetMenuBarVisibility.md)|現在の MFC アプリケーションのメニューの既定の動作を、表示または非表示に設定します。|  
|[CFrameWnd::SetMessageText](../Topic/CFrameWnd::SetMessageText.md)|標準のステータス バーのテキストを設定します。|  
|[CFrameWnd::SetProgressBarPosition](../Topic/CFrameWnd::SetProgressBarPosition.md)|タスク バーに表示される Windows 7 プログレス バーの現在の位置を設定します。|  
|[CFrameWnd::SetProgressBarRange](../Topic/CFrameWnd::SetProgressBarRange.md)|タスク バーに表示される Windows 7 プログレス バーの範囲を設定します。|  
|[CFrameWnd::SetProgressBarState](../Topic/CFrameWnd::SetProgressBarState.md)|タスク バー ボタンに表示されるプログレス インジケーターの型および状態を設定します。|  
|[CFrameWnd::SetTaskbarOverlayIcon](../Topic/CFrameWnd::SetTaskbarOverlayIcon.md)|オーバーロードされます。  タスク バー ボタンにオーバーレイを適用して、アプリケーション ステータスまたはユーザーへの通知を示します。|  
|[CFrameWnd::SetTitle](../Topic/CFrameWnd::SetTitle.md)|関連するコントロール バーのタイトルを設定します。|  
|[CFrameWnd::ShowControlBar](../Topic/CFrameWnd::ShowControlBar.md)|コントロール バーを表示します。|  
|[CFrameWnd::ShowOwnedWindows](../Topic/CFrameWnd::ShowOwnedWindows.md)|`CFrameWnd` オブジェクトの子ウィンドウ以下のすべてのウィンドウを表示します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)|フレーム用にクライアント ウィンドウを作成します。|  
|[CFrameWnd::OnHideMenuBar](../Topic/CFrameWnd::OnHideMenuBar.md)|現在の MFC アプリケーションのメニューが非表示になる前に呼び出されます。|  
|[CFrameWnd::OnShowMenuBar](../Topic/CFrameWnd::OnShowMenuBar.md)|現在の MFC アプリケーションのメニューが表示される前に呼び出されます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CFrameWnd::m\_bAutoMenuEnable](../Topic/CFrameWnd::m_bAutoMenuEnable.md)|自動的にメニュー項目の機能の入力許可と入力禁止を制御します。|  
|[CFrameWnd::rectDefault](../Topic/CFrameWnd::rectDefault.md)|Windows がウィンドウのサイズや位置の初期値を選択できるように、`CFrameWnd` オブジェクトを作成するときに、パラメーターにこの静的な `CRect` を渡します。|  
  
## 解説  
 アプリケーションのための便利なフレーム ウィンドウを作成するには、`CFrameWnd`からクラスを派生します。  アプリケーションに固有のデータを格納する、派生クラスにメンバー変数を追加します。  ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 フレーム ウィンドウを作成する方法の 3 つがあります:  
  
-   直接 [&#91;作成&#93;](../Topic/CFrameWnd::Create.md)を使用してそれを構築します。  
  
-   直接 [LoadFrame](../Topic/CFrameWnd::LoadFrame.md)を使用してそれを構築します。  
  
-   間接的にドキュメント テンプレートを使用してそれを構築します。  
  
 **\[作成\]** か `LoadFrame`を呼び出す前に、**new** C\+\+ の演算子を使用してヒープのフレーム ウィンドウ オブジェクトを構築する必要があります。  **\[作成\]**を呼び出す前に、フレームのアイコンとクラスのスタイルを設定するに [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) のグローバル関数のウィンドウ クラスを登録できます。  
  
 イミディエイト引数としてフレームの作成のパラメーターを渡すために **\[作成\]** のメンバー関数を使用します。  
  
 `LoadFrame` は **\[作成\]**ほどの引数を必要とし、フレームのキャプション、アイコン、アクセラレータ テーブルとメニューを含むリソースからなく、既定のほとんどを取得します。  `LoadFrame`にアクセスできるため、これらのリソースはすべて同じリソース id \(たとえば、**IDR\_MAINFRAME**\) が必要です。  
  
 `CFrameWnd` のオブジェクトがビュー、ドキュメントが含まれる場合、これらはプログラマの代わりに、フレームワークによって直接間接的に作成されます。  `CDocTemplate` のオブジェクトは、フレームの作成、含むビューの作成、適切なドキュメント ビューへの接続を統合します。  `CDocTemplate` のコンストラクターのパラメーターに含める 3 個のクラスの `CRuntimeClass` を指定します \(ドキュメント、ビュー、およびフレーム\)。  ユーザーによって指定されたときに、フレームワークによって `CRuntimeClass` のオブジェクトが動的に新しいフレームの作成に使用されます \(たとえば、ファイルの新しいコマンドまたはドキュメント Interface \(MDI\) の複数のウィンドウの新しいコマンドを使用\)。  
  
 `CFrameWnd` から派生したフレーム ウィンドウ クラスは `DECLARE_DYNCREATE` として宣言されて `RUNTIME_CLASS` の上記の機構が正しく動作するにする必要があります。  
  
 `CFrameWnd` は、Windows の一般的なアプリケーションのメイン ウィンドウに次の機能を実行するための既定の実装が含まれています:  
  
-   `CFrameWnd` のフレーム ウィンドウは、Windows のアクティブ ウィンドウまたは現在の入力フォーカスに依存しない現在アクティブなビューを追跡します。  フレームが再アクティブ化されたときに、アクティブなビューが `CView::OnActivateView`を呼び出して通知されます。  
  
-   `OnSetFocus`によって、`CWnd`の `OnHScroll`処理されるものも含むコマンド メッセージと、多くの一般的なフレームの通知メッセージは、現在アクティブなビューに `CFrameWnd` のフレーム ウィンドウで、`OnVScroll` 関数、転送されます。  
  
-   現在アクティブなビュー \(または MDI フレームの場合は、現在アクティブな MDI 子フレーム ウィンドウ\) フレーム ウィンドウのキャプションを確認できます。  フレーム ウィンドウの機能は、この **FWS\_ADDTOTITLE** のスタイルをオフにして無効にできます。  
  
-   `CFrameWnd` のフレーム ウィンドウは、フレーム ウィンドウのクライアント領域内のコントロール バー、ビュー、およびそのほかの子ウィンドウの配置を管理します。  フレーム ウィンドウは、ツール バーなどのコントロール バー ボタンのアイドルの更新。  `CFrameWnd` のフレーム ウィンドウに、ツール バーとステータス バーを切り替えるためのコマンドの既定の実装があります。  
  
-   `CFrameWnd` のフレーム ウィンドウは、メイン メニュー バーを実行します。  ポップアップ メニューを表示するときに、フレーム ウィンドウでは、メニュー項目が有効か無効にするか、またはチェック アウトするかを決定するために **UPDATE\_COMMAND\_UI** 機構を使用します。  ユーザーがメニュー項目を選択すると、フレーム ウィンドウは、コマンドのメッセージの文字列を含むステータス バーを更新します。  
  
-   `CFrameWnd` のフレーム ウィンドウは、省略可能なアクセラレータ テーブルを自動的によってキーボード アクセラレータがあります。  
  
-   `CFrameWnd` のフレーム ウィンドウに `LoadFrame` に設定されている状況依存のヘルプで使用される省略可能なヘルプ ID があります。  フレーム ウィンドウは状況依存のヘルプ \(Shift \+ F1 キー\) と印刷プレビュー モードなど semimodal 状態のメイン orchestrator です。  
  
-   `CFrameWnd` のフレーム ウィンドウは、ファイル マネージャーからドラッグし、フレーム ウィンドウにドロップしたファイルを開きます。  ファイル拡張子をアプリケーションに登録され、関連付けられている場合、フレーム ウィンドウは、ダイナミック データ エクスチェンジ \(DDE\) の開いている要求にユーザーがファイル マネージャーのデータ ファイルを開くか、または **ShellExecute** Windows 関数が呼び出されたときに応答します。  
  
-   フレーム ウィンドウがメイン アプリケーション ウィンドウ ユーザーがアプリケーションを閉じる場合 \(つまり、`CWinThread::m_pMainWnd`\) の場合、フレーム ウィンドウは、ユーザーが変更した文書を保存するよう要求します \( `OnClose` と `OnQueryEndSession`の場合\)。  
  
-   フレーム ウィンドウがメイン アプリケーション ウィンドウの場合は、フレーム ウィンドウは、実行中の WinHelp のコンテキストです。  このアプリケーションのヘルプに対してフレーム ウィンドウを閉じて WINHELP.EXE をシャットダウンします。  
  
 フレーム ウィンドウを破棄するときに **\[削除\]** C\+\+ の演算子を使用しないでください。  代わりに、`CWnd::DestroyWindow` を使用してください。  `PostNcDestroy` の `CFrameWnd` の実装では、ウィンドウが破棄されると、C\+\+ のオブジェクトを削除します。  ユーザーがフレーム ウィンドウを閉じると、既定の `OnClose` のハンドラーを呼び出します `DestroyWindow`。  
  
 `CFrameWnd`の詳細については、[フレーム ウィンドウ](../../mfc/frame-windows.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CFrameWnd`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)   
 [CView クラス](../Topic/CView%20Class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass 構造体](../Topic/CRuntimeClass%20Structure.md)