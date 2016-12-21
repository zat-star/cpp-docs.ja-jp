---
title: "CWindow クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CWindow"
  - "ATL::CWindow"
  - "CWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindow クラス"
ms.assetid: fefa00c8-f053-4bcf-87bc-dc84f5386683
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWindow クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ウィンドウを操作するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CWindow  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CWindow::CWindow](../Topic/CWindow::CWindow.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWindow::ArrangeIconicWindows](../Topic/CWindow::ArrangeIconicWindows.md)|最小化されたすべての子ウィンドウを並べ替えます。|  
|[CWindow::Attach](../Topic/CWindow::Attach.md)|`CWindow` のウィンドウをオブジェクトにアタッチします。|  
|[CWindow::BeginPaint](../Topic/CWindow::BeginPaint.md)|描画用にウィンドウを準備します。|  
|[CWindow::BringWindowToTop](../Topic/CWindow::BringWindowToTop.md)|z 軸順番の上にウィンドウが表示されます。|  
|[CWindow::CenterWindow](../Topic/CWindow::CenterWindow.md)|特定のウィンドウに対してウィンドウを中央揃えにします。|  
|[CWindow::ChangeClipboardChain](../Topic/CWindow::ChangeClipboardChain.md)|クリップボード ビューアーのチェインからペインを削除します。|  
|[CWindow::CheckDlgButton](../Topic/CWindow::CheckDlgButton.md)|指定したボタンのチェック状態を変更します。|  
|[CWindow::CheckRadioButton](../Topic/CWindow::CheckRadioButton.md)|指定したラジオ ボタンをチェックします。|  
|[CWindow::ChildWindowFromPoint](../Topic/CWindow::ChildWindowFromPoint.md)|指定した点を含む子ウィンドウを取得します。|  
|[CWindow::ChildWindowFromPointEx](../Topic/CWindow::ChildWindowFromPointEx.md)|指定した点を含む子ウィンドウの特定の型を取得します。|  
|[CWindow::ClientToScreen](../Topic/CWindow::ClientToScreen.md)|クライアント座標の座標を除外するに変換します。|  
|[CWindow::Create](../Topic/CWindow::Create.md)|ウィンドウを作成します。|  
|[CWindow::CreateCaret](../Topic/CWindow::CreateCaret.md)|システム キャレットの新しい図形を作成します。|  
|[CWindow::CreateGrayCaret](../Topic/CWindow::CreateGrayCaret.md)|システム キャレットの灰色の四角形を作成します。|  
|[CWindow::CreateSolidCaret](../Topic/CWindow::CreateSolidCaret.md)|システム キャレットの実線の四角形を作成します。|  
|[CWindow::DeferWindowPos](../Topic/CWindow::DeferWindowPos.md)|指定されたペインに複数指定のウィンドウ位置構造体を更新します。|  
|[CWindow::DestroyWindow](../Topic/CWindow::DestroyWindow.md)|`CWindow` のオブジェクトに関連付けられたウィンドウを破棄します。|  
|[CWindow::Detach](../Topic/CWindow::Detach.md)|`CWindow` のオブジェクトからウィンドウをデタッチします。|  
|[CWindow::DlgDirList](../Topic/CWindow::DlgDirList.md)|指定したパスまたはファイル名に一致するすべてのファイルの名前のリスト ボックスを塗りつぶします。|  
|[CWindow::DlgDirListComboBox](../Topic/CWindow::DlgDirListComboBox.md)|指定したパスまたはファイル名に一致するすべてのファイルの名前を持つコンボ ボックスを塗りつぶします。|  
|[CWindow::DlgDirSelect](../Topic/CWindow::DlgDirSelect.md)|リスト ボックスから現在の選択内容を取得します。|  
|[CWindow::DlgDirSelectComboBox](../Topic/CWindow::DlgDirSelectComboBox.md)|コンボ ボックスから現在の選択を取得します。|  
|[CWindow::DragAcceptFiles](../Topic/CWindow::DragAcceptFiles.md)|ウィンドウがドラッグ ファイルを受け入れるかどうかを登録します。|  
|[CWindow::DrawMenuBar](../Topic/CWindow::DrawMenuBar.md)|ウィンドウのメニュー バーを再描画します。|  
|[CWindow::EnableScrollBar](../Topic/CWindow::EnableScrollBar.md)|スクロール バーの矢印を有効または無効にします。|  
|[CWindow::EnableWindow](../Topic/CWindow::EnableWindow.md)|入力を有効または無効にします。|  
|[CWindow::EndPaint](../Topic/CWindow::EndPaint.md)|描画の終了を示します。|  
|[CWindow::FlashWindow](../Topic/CWindow::FlashWindow.md)|ウィンドウを 1 回フラッシュします。|  
|[CWindow::GetClientRect](../Topic/CWindow::GetClientRect.md)|クライアント領域の座標を取得します。|  
|[CWindow::GetDC](../Topic/CWindow::GetDC.md)|クライアント領域のデバイス コンテキストを取得します。|  
|[CWindow::GetDCEx](../Topic/CWindow::GetDCEx.md)|クライアント領域のデバイス コンテキストを取得し、オプションをクリップ割り当てます。|  
|[CWindow::GetDescendantWindow](../Topic/CWindow::GetDescendantWindow.md)|指定の子孫ウィンドウを取得します。|  
|[CWindow::GetDlgControl](../Topic/CWindow::GetDlgControl.md)|指定されたコントロールのインターフェイスを取得します。|  
|[CWindow::GetDlgCtrlID](../Topic/CWindow::GetDlgCtrlID.md)|ウィンドウの識別子を取得します \(子ウィンドウの場合のみ\)。|  
|[CWindow::GetDlgHost](../Topic/CWindow::GetDlgHost.md)|ATL のコントロール ホスト コンテナーにインターフェイスへのポインターを取得します。|  
|[CWindow::GetDlgItem](../Topic/CWindow::GetDlgItem.md)|指定された子ウィンドウを取得します。|  
|[CWindow::GetDlgItemInt](../Topic/CWindow::GetDlgItemInt.md)|コントロールのテキストを整数に変換します。|  
|[CWindow::GetDlgItemText](../Topic/CWindow::GetDlgItemText.md)|コントロールのテキストを取得します。|  
|[CWindow::GetExStyle](../Topic/CWindow::GetExStyle.md)|拡張ウィンドウ スタイルを取得します。|  
|[CWindow::GetFont](../Topic/CWindow::GetFont.md)|ウィンドウの現在のフォントを取得します。|  
|[CWindow::GetHotKey](../Topic/CWindow::GetHotKey.md)|ウィンドウに関連付けられているホット キーを決定します。|  
|[CWindow::GetIcon](../Topic/CWindow::GetIcon.md)|ウィンドウで、大きいアイコンまたは小さいアイコンを取得します。|  
|[CWindow::GetLastActivePopup](../Topic/CWindow::GetLastActivePopup.md)|最近アクティブなポップアップ ウィンドウを取得します。|  
|[CWindow::GetMenu](../Topic/CWindow::GetMenu.md)|ウィンドウ メニューを取得します。|  
|[CWindow::GetNextDlgGroupItem](../Topic/CWindow::GetNextDlgGroupItem.md)|コントロールのグループ内で前後のコントロールを取得します。|  
|[CWindow::GetNextDlgTabItem](../Topic/CWindow::GetNextDlgTabItem.md)|**WS\_TABSTOP** のスタイルを持つ前後のコントロールを取得します。|  
|[CWindow::GetParent](../Topic/CWindow::GetParent.md)|直接の親ウィンドウを取得します。|  
|[CWindow::GetScrollInfo](../Topic/CWindow::GetScrollInfo.md)|スクロール バーのパラメーターを取得します。|  
|[CWindow::GetScrollPos](../Topic/CWindow::GetScrollPos.md)|スクロール ボックスの位置を取得します。|  
|[CWindow::GetScrollRange](../Topic/CWindow::GetScrollRange.md)|スクロール バーの範囲を取得します。|  
|[CWindow::GetStyle](../Topic/CWindow::GetStyle.md)|ウィンドウ スタイルを取得します。|  
|[CWindow::GetSystemMenu](../Topic/CWindow::GetSystemMenu.md)|変更対象のシステム メニューのコピーを作成します。|  
|[CWindow::GetTopLevelParent](../Topic/CWindow::GetTopLevelParent.md)|トップレベルの親ウィンドウまたはオーナー ウィンドウを取得します。|  
|[CWindow::GetTopLevelWindow](../Topic/CWindow::GetTopLevelWindow.md)|トップレベルのオーナー ウィンドウを取得します。|  
|[CWindow::GetTopWindow](../Topic/CWindow::GetTopWindow.md)|トップレベルの子ウィンドウを取得します。|  
|[CWindow::GetUpdateRect](../Topic/CWindow::GetUpdateRect.md)|完全に更新領域を囲む最小の四角形の座標を取得します。|  
|[CWindow::GetUpdateRgn](../Topic/CWindow::GetUpdateRgn.md)|更新領域を取得し、指定した領域にコピーします。|  
|[CWindow::GetWindow](../Topic/CWindow::GetWindow.md)|指定されたウィンドウを取得します。|  
|[CWindow::GetWindowContextHelpId](../Topic/CWindow::GetWindowContextHelpId.md)|ウィンドウのヘルプ コンテキスト識別子を取得します。|  
|[CWindow::GetWindowDC](../Topic/CWindow::GetWindowDC.md)|ウィンドウ全体のデバイス コンテキストを取得します。|  
|[CWindow::GetWindowLong](../Topic/CWindow::GetWindowLong.md)|余分なウィンドウのメモリへの指定したオフセット位置に 32 ビット値を取得します。|  
|[CWindow::GetWindowLongPtr](../Topic/CWindow::GetWindowLongPtr.md)|余分なウィンドウのメモリへの指定したオフセット位置に値を含めて、指定したウィンドウに関する情報を取得します。|  
|[CWindow::GetWindowPlacement](../Topic/CWindow::GetWindowPlacement.md)|表示状態と位置を取得します。|  
|[CWindow::GetWindowProcessID](../Topic/CWindow::GetWindowProcessID.md)|ウィンドウを作成したプロセスの識別子を取得します。|  
|[CWindow::GetWindowRect](../Topic/CWindow::GetWindowRect.md)|ウィンドウの外接する次元を取得します。|  
|[CWindow::GetWindowRgn](../Topic/CWindow::GetWindowRgn.md)|ウィンドウのウィンドウ領域のコピーを取得します。|  
|[CWindow::GetWindowText](../Topic/CWindow::GetWindowText.md)|ウィンドウのテキストを取得します。|  
|[CWindow::GetWindowTextLength](../Topic/CWindow::GetWindowTextLength.md)|ウィンドウのテキストの長さを取得します。|  
|[CWindow::GetWindowThreadID](../Topic/CWindow::GetWindowThreadID.md)|指定されたウィンドウを作成したスレッド識別子を取得します。|  
|[CWindow::GetWindowWord](../Topic/CWindow::GetWindowWord.md)|余分なウィンドウのメモリへの指定したオフセット位置に 16 ビット値を取得します。|  
|[CWindow::GotoDlgCtrl](../Topic/CWindow::GotoDlgCtrl.md)|ダイアログ ボックス コントロールにキーボード フォーカスを設定します。|  
|[CWindow::HideCaret](../Topic/CWindow::HideCaret.md)|システム キャレットを非表示にします。|  
|[CWindow::HiliteMenuItem](../Topic/CWindow::HiliteMenuItem.md)|強調表示または削除トップレベル メニュー項目の強調表示されます。|  
|[CWindow::Invalidate](../Topic/CWindow::Invalidate.md)|クライアント領域全体を無効にします。|  
|[CWindow::InvalidateRect](../Topic/CWindow::InvalidateRect.md)|指定された四角形内のクライアント領域を無効にします。|  
|[CWindow::InvalidateRgn](../Topic/CWindow::InvalidateRgn.md)|指定領域内のクライアント領域を無効にします。|  
|[CWindow::IsChild](../Topic/CWindow::IsChild.md)|指定されたウィンドウが子ウィンドウであるかどうかを判定します。|  
|[CWindow::IsDialogMessage](../Topic/CWindow::IsDialogMessage.md)|メッセージが指定されたダイアログ ボックスを想定しているかどうかを判定します。|  
|[CWindow::IsDlgButtonChecked](../Topic/CWindow::IsDlgButtonChecked.md)|ボタンのチェック状態を決定します。|  
|[CWindow::IsIconic](../Topic/CWindow::IsIconic.md)|ウィンドウが最小化されているかどうかを判定します。|  
|[CWindow::IsParentDialog](../Topic/CWindow::IsParentDialog.md)|コントロールの親ウィンドウがダイアログのウィンドウかどうかを判定します。|  
|[CWindow::IsWindow](../Topic/CWindow::IsWindow.md)|指定されたウィンドウ ハンドルが既存のウィンドウを識別するかどうかを判定します。|  
|[CWindow::IsWindowEnabled](../Topic/CWindow::IsWindowEnabled.md)|ウィンドウが入力が有効かどうかを判定します。|  
|[CWindow::IsWindowUnicode](../Topic/CWindow::IsWindowUnicode.md)|指定されたウィンドウがネイティブな Unicode ウィンドウかどうかを判定します。|  
|[CWindow::IsWindowVisible](../Topic/CWindow::IsWindowVisible.md)|ウィンドウの表示状態が決まります。|  
|[CWindow::IsZoomed](../Topic/CWindow::IsZoomed.md)|ウィンドウが最大化するかどうかを判定します。|  
|[CWindow::KillTimer](../Topic/CWindow::KillTimer.md)|タイマー イベントを破棄します。|  
|[CWindow::LockWindowUpdate](../Topic/CWindow::LockWindowUpdate.md)|無効、またはウィンドウの描画を有効にします。|  
|[CWindow::MapWindowPoints](../Topic/CWindow::MapWindowPoints.md)|ウィンドウの座標空間から別のウィンドウの座標空間への複数の点を変換します。|  
|[CWindow::MessageBox](../Topic/CWindow::MessageBox.md)|メッセージ ボックスを表示します。|  
|[CWindow::ModifyStyle](../Topic/CWindow::ModifyStyle.md)|ウィンドウ スタイルを変更します。|  
|[CWindow::ModifyStyleEx](../Topic/CWindow::ModifyStyleEx.md)|拡張ウィンドウ スタイルを変更します。|  
|[CWindow::MoveWindow](../Topic/CWindow::MoveWindow.md)|ウィンドウのサイズと位置を変更します。|  
|[CWindow::NextDlgCtrl](../Topic/CWindow::NextDlgCtrl.md)|ダイアログ ボックスで次のコントロールにキーボード フォーカスを設定します。|  
|[CWindow::OpenClipboard](../Topic/CWindow::OpenClipboard.md)|クリップボードを開きます。|  
|[CWindow::PostMessage](../Topic/CWindow::PostMessage.md)|ウィンドウを作成したスレッドに関連付けられたメッセージ キューにメッセージを設定します。  スレッドがメッセージを処理するのを待たずに返します。|  
|[CWindow::PrevDlgCtrl](../Topic/CWindow::PrevDlgCtrl.md)|ダイアログ ボックスで一つ前のコントロールにキーボード フォーカスを設定します。|  
|[CWindow::Print](../Topic/CWindow::Print.md)|その要求は、指定されたデバイス コンテキスト ウィンドウで描画します。|  
|[CWindow::PrintClient](../Topic/CWindow::PrintClient.md)|その要求は、指定されたデバイス コンテキストでウィンドウのクライアント領域描画します。|  
|[CWindow::RedrawWindow](../Topic/CWindow::RedrawWindow.md)|クライアント領域の指定された四角形または領域を更新します。|  
|[CWindow::ReleaseDC](../Topic/CWindow::ReleaseDC.md)|デバイス コンテキストを解放します。|  
|[CWindow::ResizeClient](../Topic/CWindow::ResizeClient.md)|ウィンドウのサイズを変更します。|  
|[CWindow::ScreenToClient](../Topic/CWindow::ScreenToClient.md)|クライアント座標への変換の画面座標。|  
|[CWindow::ScrollWindow](../Topic/CWindow::ScrollWindow.md)|指定されたクライアント領域をスクロールします。|  
|[CWindow::ScrollWindowEx](../Topic/CWindow::ScrollWindowEx.md)|追加機能で指定されたクライアント領域をスクロールします。|  
|[CWindow::SendDlgItemMessage](../Topic/CWindow::SendDlgItemMessage.md)|コントロールにメッセージを送信します。|  
|[CWindow::SendMessage](../Topic/CWindow::SendMessage.md)|ウィンドウ プロシージャでメッセージが処理されるまでメッセージをウィンドウに送信し、を返します。|  
|[CWindow::SendMessageToDescendants](../Topic/CWindow::SendMessageToDescendants.md)|指定の子孫ウィンドウにメッセージを送信します。|  
|[CWindow::SendNotifyMessage](../Topic/CWindow::SendNotifyMessage.md)|ウィンドウにメッセージを送信します。  ウィンドウが呼び出し元のスレッドによって作成された場合、`SendNotifyMessage` はウィンドウ プロシージャがメッセージを処理するまで制御を戻しません。  それ以外の場合はすぐに制御を返します。|  
|[CWindow::SetActiveWindow](../Topic/CWindow::SetActiveWindow.md)|ウィンドウをアクティブにします。|  
|[CWindow::SetCapture](../Topic/CWindow::SetCapture.md)|入力ウィンドウに後続のすべてのマウスを送信します。|  
|[CWindow::SetClipboardViewer](../Topic/CWindow::SetClipboardViewer.md)|クリップボード ビューアーのチェインにペインを追加します。|  
|[CWindow::SetDlgCtrlID](../Topic/CWindow::SetDlgCtrlID.md)|ウィンドウの識別子を変更します。|  
|[CWindow::SetDlgItemInt](../Topic/CWindow::SetDlgItemInt.md)|整数値の文字列表現にコントロールのテキストを変更します。|  
|[CWindow::SetDlgItemText](../Topic/CWindow::SetDlgItemText.md)|コントロールのテキストを変更します。|  
|[CWindow::SetFocus](../Topic/CWindow::SetFocus.md)|ウィンドウに入力フォーカスを設定します。|  
|[CWindow::SetFont](../Topic/CWindow::SetFont.md)|ウィンドウの現在のフォントを変更します。|  
|[CWindow::SetHotKey](../Topic/CWindow::SetHotKey.md)|ウィンドウでホット キーを関連付けます。|  
|[CWindow::SetIcon](../Topic/CWindow::SetIcon.md)|ウィンドウで、大きいアイコンまたは小さいアイコンを変更します。|  
|[CWindow::SetMenu](../Topic/CWindow::SetMenu.md)|ウィンドウの現在のメニューを変更します。|  
|[CWindow::SetParent](../Topic/CWindow::SetParent.md)|親ウィンドウを変更します。|  
|[CWindow::SetRedraw](../Topic/CWindow::SetRedraw.md)|をオンまたはオフに再描画のフラグ。|  
|[CWindow::SetScrollInfo](../Topic/CWindow::SetScrollInfo.md)|スクロール バーのパラメーターを設定します。|  
|[CWindow::SetScrollPos](../Topic/CWindow::SetScrollPos.md)|スクロール ボックスの位置を変更します。|  
|[CWindow::SetScrollRange](../Topic/CWindow::SetScrollRange.md)|スクロール バーの範囲を変更します。|  
|[CWindow::SetTimer](../Topic/CWindow::SetTimer.md)|タイマー イベントを作成します。|  
|[CWindow::SetWindowContextHelpId](../Topic/CWindow::SetWindowContextHelpId.md)|ウィンドウのヘルプ コンテキスト識別子を設定します。|  
|[CWindow::SetWindowLong](../Topic/CWindow::SetWindowLong.md)|余分なウィンドウのメモリへの指定したオフセット位置に 32 ビット値を設定します。|  
|[CWindow::SetWindowLongPtr](../Topic/CWindow::SetWindowLongPtr.md)|指定されたペインの属性を変更、追加のウィンドウでメモリの指定したオフセット位置に値を設定します。|  
|[CWindow::SetWindowPlacement](../Topic/CWindow::SetWindowPlacement.md)|表示状態と位置を設定します。|  
|[CWindow::SetWindowPos](../Topic/CWindow::SetWindowPos.md)|サイズ、位置、および Z 軸順番を設定します。|  
|[CWindow::SetWindowRgn](../Topic/CWindow::SetWindowRgn.md)|ウィンドウのウィンドウ領域を設定します。|  
|[CWindow::SetWindowText](../Topic/CWindow::SetWindowText.md)|ウィンドウのテキストを変更します。|  
|[CWindow::SetWindowWord](../Topic/CWindow::SetWindowWord.md)|余分なウィンドウのメモリへの指定したオフセット位置に 16 ビット値を設定します。|  
|[CWindow::ShowCaret](../Topic/CWindow::ShowCaret.md)|システム キャレットが表示されます。|  
|[CWindow::ShowOwnedPopups](../Topic/CWindow::ShowOwnedPopups.md)|ウィンドウを表示または非表示によって所有されるポップアップ ウィンドウ。|  
|[CWindow::ShowScrollBar](../Topic/CWindow::ShowScrollBar.md)|スクロール バーを表示または非表示にします。|  
|[CWindow::ShowWindow](../Topic/CWindow::ShowWindow.md)|ウィンドウの表示状態を設定します。|  
|[CWindow::ShowWindowAsync](../Topic/CWindow::ShowWindowAsync.md)|他のスレッドによって作成されたペインの表示状態を設定します。|  
|[CWindow::UpdateWindow](../Topic/CWindow::UpdateWindow.md)|クライアント領域を更新します。|  
|[CWindow::ValidateRect](../Topic/CWindow::ValidateRect.md)|指定された四角形内のクライアント領域を有効にします。|  
|[CWindow::ValidateRgn](../Topic/CWindow::ValidateRgn.md)|指定領域内のクライアント領域を有効にします。|  
|[CWindow::WinHelp](../Topic/CWindow::WinHelp.md)|Windows ヘルプの開始。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CWindow::operator HWND](../Topic/CWindow::operator%20HWND.md)|`HWND`への `CWindow` のオブジェクトを変換します。|  
|[CWindow::operator \=](../Topic/CWindow::operator%20=.md)|`CWindow` のオブジェクトに `HWND` を割り当てます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CWindow::m\_hWnd](../Topic/CWindow::m_hWnd.md)|`CWindow` のオブジェクトに関連付けられたウィンドウへのハンドル。|  
|[CWindow::rcDefault](../Topic/CWindow::rcDefault.md)|既定のウィンドウのサイズが含まれています。|  
  
## 解説  
 `CWindow` は、ATL ウィンドウを操作するための基本機能を提供します。  `CWindow` のメソッドの多くは、Win32 API の関数の 1 種類だけをラップします。  たとえば、`CWindow::ShowWindow` と `ShowWindow`のプロトタイプを比較する:  
  
|CWindow のメソッド|Win32 関数|  
|-------------------|--------------|  
|**BOOL ShowWindow\( int**  `nCmdShow`\) ;|**BOOL ShowWindow\( HWND**  `hWnd` **, int**  `nCmdShow`\) ;|  
  
 `CWindow::ShowWindow` は最初のパラメーターとして `CWindow::m_hWnd` を渡すことによって `ShowWindow` Win32 関数を呼び出します。  直接 Win32 関数をラップする `CWindow` のメソッドは `m_hWnd` のメンバーを渡します; したがって、`CWindow` のドキュメントの多くは [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]が表示されます。  
  
> [!NOTE]
>  `CWindow`と `CWindow` のメソッドのラップして、ウィンドウに関連する Win32 関数が Win32 関数ラップされません。  
  
 `CWindow::m_hWnd` は `HWND` を格納するウィンドウを識別します。  `HWND` は、オブジェクトにアタッチされます:場合  
  
-   `CWindow` のコンストラクターで `HWND` を指定します。  
  
-   `CWindow::Attach` を呼び出します。  
  
-   `CWindow` の **operator \=**を使用します。  
  
-   作成するか、次のクラスの 1 つがを使用してウィンドウがサブクラス:から派生 `CWindow`  
  
     [CWindowImpl](../Topic/CWindowImpl%20Class.md) は、既存のウィンドウ新しいウィンドウまたはサブクラスを作成することができます。  
  
     [CContainedWindow](../Topic/CContainedWindowT%20Class.md) は別のオブジェクトに含まれているウィンドウを実装します。  既存のウィンドウ新しいウィンドウまたはサブクラスを作成できます。  
  
     [CDialogImpl](../Topic/CDialogImpl%20Class.md) はモーダルまたはモードレス ダイアログ ボックスを作成できるようにします。  
  
 ウィンドウの詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [\[ウィンドウ\]](http://msdn.microsoft.com/library/windows/desktop/ms632595) それ以降のトピックを参照してください。  ATL でウィンドウを使用する方法の詳細については、" " [ATL ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)