---
title: "CToolBarCtrl クラス | Microsoft Docs"
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
  - "CToolBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl クラス"
  - "ツール ヒント [C++], 通知"
  - "ツール バー コントロール [MFC], CToolBarCtrl クラス"
  - "Windows コモン コントロール [C++], CToolBarCtrl"
ms.assetid: 8f2f8ad2-05d7-4975-8715-3f2eed795248
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CToolBarCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows ツール バー コモン コントロールの機能が用意されています。  
  
## 構文  
  
```  
class CToolBarCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CToolBarCtrl::CToolBarCtrl](../Topic/CToolBarCtrl::CToolBarCtrl.md)|`CToolBarCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CToolBarCtrl::AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md)|ツール バー コントロールで使用できるボタン イメージのリストに一つ以上のビットマップ ボタンのイメージを追加します。|  
|[CToolBarCtrl::AddButtons](../Topic/CToolBarCtrl::AddButtons.md)|ツール バー コントロールに一つ以上のボタンを追加します。|  
|[CToolBarCtrl::AddString](../Topic/CToolBarCtrl::AddString.md)|リソース id として渡されたツール バーの文字列の内部リストに新しい文字列を追加します。|  
|[CToolBarCtrl::AddStrings](../Topic/CToolBarCtrl::AddStrings.md)|null 区切り文字列バッファーとして渡されるポインター ツール バーの文字列の内部リストに新しい文字列を追加します。|  
|[CToolBarCtrl::AutoSize](../Topic/CToolBarCtrl::AutoSize.md)|ツール バー コントロールのサイズを変更します。|  
|[CToolBarCtrl::ChangeBitmap](../Topic/CToolBarCtrl::ChangeBitmap.md)|現在のツール バー コントロールのボタンのビットマップを変更します。|  
|[CToolBarCtrl::CheckButton](../Topic/CToolBarCtrl::CheckButton.md)|チェックまたはクリアします。ツール バー コントロールのボタン。|  
|[CToolBarCtrl::CommandToIndex](../Topic/CToolBarCtrl::CommandToIndex.md)|指定したコマンド ID に関連付けられたボタン用のインデックスを取得します。|  
|[CToolBarCtrl::Create](../Topic/CToolBarCtrl::Create.md)|ツール バー コントロールを作成し、`CToolBarCtrl` のオブジェクトにアタッチします。|  
|[CToolBarCtrl::CreateEx](../Topic/CToolBarCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルのツール バー コントロールを作成し、`CToolBarCtrl` のオブジェクトにアタッチします。|  
|[CToolBarCtrl::Customize](../Topic/CToolBarCtrl::Customize.md)|ツール バーのカスタマイズ ダイアログ ボックスを表示します。|  
|[CToolBarCtrl::DeleteButton](../Topic/CToolBarCtrl::DeleteButton.md)|ツール バー コントロールのボタンを削除します。|  
|[CToolBarCtrl::EnableButton](../Topic/CToolBarCtrl::EnableButton.md)|ツール バーの指定コントロール ボタンを有効または無効にします。|  
|[CToolBarCtrl::GetAnchorHighlight](../Topic/CToolBarCtrl::GetAnchorHighlight.md)|ツール バーのアンカーの強調表示の設定を取得します。|  
|[CToolBarCtrl::GetBitmap](../Topic/CToolBarCtrl::GetBitmap.md)|ツール バー ボタンに関連付けられたビットマップのインデックスを取得します。|  
|[CToolBarCtrl::GetBitmapFlags](../Topic/CToolBarCtrl::GetBitmapFlags.md)|フラグをツール バー ビットマップに関連付けられているを取得します。|  
|[CToolBarCtrl::GetButton](../Topic/CToolBarCtrl::GetButton.md)|ツール バー ボタン コントロールの指定に関する情報を取得します。|  
|[CToolBarCtrl::GetButtonCount](../Topic/CToolBarCtrl::GetButtonCount.md)|ツール バー コントロール ボタンの数を現在取得します。|  
|[CToolBarCtrl::GetButtonInfo](../Topic/CToolBarCtrl::GetButtonInfo.md)|ツール バー ボタンの情報を取得します。|  
|[CToolBarCtrl::GetButtonSize](../Topic/CToolBarCtrl::GetButtonSize.md)|ピクセルのツール バー ボタンの現在の幅と高さを取得します。|  
|[CToolBarCtrl::GetColorScheme](../Topic/CToolBarCtrl::GetColorScheme.md)|現在のツール バー コントロールの配色を取得します。|  
|[CToolBarCtrl::GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md)|無効なボタンを表示する場合は、ツール バー コントロールが使用するイメージ リストを取得します。|  
|[CToolBarCtrl::GetDropTarget](../Topic/CToolBarCtrl::GetDropTarget.md)|ツール バー コントロールの [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) のインターフェイスを取得します。|  
|[CToolBarCtrl::GetExtendedStyle](../Topic/CToolBarCtrl::GetExtendedStyle.md)|ツール バー コントロールの拡張スタイルを取得します。|  
|[CToolBarCtrl::GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md)|「ホット」ボタンを表示する場合は、ツール バー コントロールが使用するイメージ リストを取得します。  ホット ボタンは、マウス ポインターは、の上にあることを強調表示されます。|  
|[CToolBarCtrl::GetHotItem](../Topic/CToolBarCtrl::GetHotItem.md)|ツール バーのホット項目のインデックスを取得します。|  
|[CToolBarCtrl::GetImageList](../Topic/CToolBarCtrl::GetImageList.md)|既定のボタンを表示する場合は、ツール バー コントロールが使用するイメージ リストを取得します。|  
|[CToolBarCtrl::GetInsertMark](../Topic/CToolBarCtrl::GetInsertMark.md)|ツール バーの現在の挿入マークを取得します。|  
|[CToolBarCtrl::GetInsertMarkColor](../Topic/CToolBarCtrl::GetInsertMarkColor.md)|ツール バーの挿入マークの描画色を取得します。|  
|[CToolBarCtrl::GetItemRect](../Topic/CToolBarCtrl::GetItemRect.md)|ツール バー コントロール ボタンの外接する四角形を取得します。|  
|[CToolBarCtrl::GetMaxSize](../Topic/CToolBarCtrl::GetMaxSize.md)|ツール バーに表示されるボタンと区切りすべての合計サイズを取得します。|  
|[CToolBarCtrl::GetMaxTextRows](../Topic/CToolBarCtrl::GetMaxTextRows.md)|ツール バー ボタンに表示されるテキストの行の最大数を取得します。|  
|[CToolBarCtrl::GetMetrics](../Topic/CToolBarCtrl::GetMetrics.md)|ツール バー コントロールのメトリックを取得します。|  
|[CToolBarCtrl::GetPadding](../Topic/CToolBarCtrl::GetPadding.md)|現在のツール バー コントロールの水平方向と垂直方向の埋め込みを取得します。|  
|[CToolBarCtrl::GetPressedImageList](../Topic/CToolBarCtrl::GetPressedImageList.md)|押された状態のボタンを表すために現在のツール バー コントロールが使用するイメージ リストを取得します。|  
|[CToolBarCtrl::GetRect](../Topic/CToolBarCtrl::GetRect.md)|指定されたツール バー ボタンの外接する四角形を取得します。|  
|[CToolBarCtrl::GetRows](../Topic/CToolBarCtrl::GetRows.md)|現在ツール バーに表示されるボタンの行数を取得します。|  
|[CToolBarCtrl::GetState](../Topic/CToolBarCtrl::GetState.md)|有効にするか、押された場合はオンにするかどうかをツール バー コントロール内の指定されたボタンの状態に関する情報を、のような取得します。|  
|[CToolBarCtrl::GetString](../Topic/CToolBarCtrl::GetString.md)|ツール バーの文字列を取得します。|  
|[CToolBarCtrl::GetStyle](../Topic/CToolBarCtrl::GetStyle.md)|ツール バー コントロールに現在使用中のスタイルを取得します。|  
|[CToolBarCtrl::GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md)|ある場合は、ツール バー コントロールに関連付けられているツール ヒント コントロールのハンドルを取得します。|  
|[CToolBarCtrl::HideButton](../Topic/CToolBarCtrl::HideButton.md)|非表示を切り替えツール バー ボタン コントロールの指定。|  
|[CToolBarCtrl::HitTest](../Topic/CToolBarCtrl::HitTest.md)|ポイントがツール バー コントロールのどこにあるかを判断します。|  
|[CToolBarCtrl::Indeterminate](../Topic/CToolBarCtrl::Indeterminate.md)|設定またはクリアします。ツール バー コントロールのボタンの書式指定 \(灰色\) の状態。|  
|[CToolBarCtrl::InsertButton](../Topic/CToolBarCtrl::InsertButton.md)|ツール バー コントロール ボタンを挿入します。|  
|[CToolBarCtrl::InsertMarkHitTest](../Topic/CToolBarCtrl::InsertMarkHitTest.md)|ツール バーのポイントの挿入マークの情報を取得します。|  
|[CToolBarCtrl::IsButtonChecked](../Topic/CToolBarCtrl::IsButtonChecked.md)|ツール バーの指定コントロール ボタンがオンになっているかどうかを示します。|  
|[CToolBarCtrl::IsButtonEnabled](../Topic/CToolBarCtrl::IsButtonEnabled.md)|ツール バー ボタン コントロールの指定が有効かどうかを示します。|  
|[CToolBarCtrl::IsButtonHidden](../Topic/CToolBarCtrl::IsButtonHidden.md)|ツール バーの指定コントロール ボタンが非表示かどうかを示します。|  
|[CToolBarCtrl::IsButtonHighlighted](../Topic/CToolBarCtrl::IsButtonHighlighted.md)|ツール バー ボタンの強調表示状態をチェックします。|  
|[CToolBarCtrl::IsButtonIndeterminate](../Topic/CToolBarCtrl::IsButtonIndeterminate.md)|ツール バーの指定コントロール ボタンの状態が呼び出されるかどうかも示します \(灰色\)。|  
|[CToolBarCtrl::IsButtonPressed](../Topic/CToolBarCtrl::IsButtonPressed.md)|ツール バーの指定コントロール ボタンが押されたかどうかを示します。|  
|[CToolBarCtrl::LoadImages](../Topic/CToolBarCtrl::LoadImages.md)|ツール バーのイメージ リストへの読み込みのビットマップ。|  
|[CToolBarCtrl::MapAccelerator](../Topic/CToolBarCtrl::MapAccelerator.md)|ツール バー ボタンにアクセラレータの文字をマップします。|  
|[CToolBarCtrl::MarkButton](../Topic/CToolBarCtrl::MarkButton.md)|ツール バー コントロールのボタンの強調表示状態を設定します。|  
|[CToolBarCtrl::MoveButton](../Topic/CToolBarCtrl::MoveButton.md)|1 種類のインデックスから別のツール バーにボタンを実行します。|  
|[CToolBarCtrl::PressButton](../Topic/CToolBarCtrl::PressButton.md)|Enter キーまたはリリース ツール バー ボタン コントロールの指定。|  
|[CToolBarCtrl::ReplaceBitmap](../Topic/CToolBarCtrl::ReplaceBitmap.md)|新しいビットマップと現在のツール バー コントロールの既存のビットマップを置き換えます。|  
|[CToolBarCtrl::RestoreState](../Topic/CToolBarCtrl::RestoreState.md)|ツール バー コントロールの状態を復元します。|  
|[CToolBarCtrl::SaveState](../Topic/CToolBarCtrl::SaveState.md)|ツール バー コントロールの状態を保存します。|  
|[CToolBarCtrl::SetAnchorHighlight](../Topic/CToolBarCtrl::SetAnchorHighlight.md)|ツール バーのアンカーの強調表示を設定します。|  
|[CToolBarCtrl::SetBitmapSize](../Topic/CToolBarCtrl::SetBitmapSize.md)|ツール バー コントロールに追加するビットマップ イメージのサイズを設定します。|  
|[CToolBarCtrl::SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)|ツール バーの既存のボタンの情報を設定します。|  
|[CToolBarCtrl::SetButtonSize](../Topic/CToolBarCtrl::SetButtonSize.md)|ツール バー コントロールに追加するボタンのサイズを設定します。|  
|[CToolBarCtrl::SetButtonStructSize](../Topic/CToolBarCtrl::SetButtonStructSize.md)|`TBBUTTON` の構造体のサイズを指定します。|  
|[CToolBarCtrl::SetButtonWidth](../Topic/CToolBarCtrl::SetButtonWidth.md)|ツール バーの最小値と最大のボタンの幅を設定します。|  
|[CToolBarCtrl::SetCmdID](../Topic/CToolBarCtrl::SetCmdID.md)|指定したボタンを押すと、オーナー ウィンドウに送信されるコマンド ID を設定します。|  
|[CToolBarCtrl::SetColorScheme](../Topic/CToolBarCtrl::SetColorScheme.md)|現在のツール バー コントロールの配色を設定します。|  
|[CToolBarCtrl::SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md)|無効なボタンを表示する場合は、ツール バー コントロールが使用するイメージ リストを設定します。|  
|[CToolBarCtrl::SetDrawTextFlags](../Topic/CToolBarCtrl::SetDrawTextFlags.md)|書式設定する Win32 関数 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498)のフラグがどのように設定するためのフラグを指定して、テキストを四角形内に描画に使用する設定します。|  
|[CToolBarCtrl::SetExtendedStyle](../Topic/CToolBarCtrl::SetExtendedStyle.md)|ツール バー コントロールの拡張スタイルを設定します。|  
|[CToolBarCtrl::SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md)|「ホット」ボタンを表示する場合は、ツール バー コントロールが使用するイメージ リストを設定します。|  
|[CToolBarCtrl::SetHotItem](../Topic/CToolBarCtrl::SetHotItem.md)|ツール バーのホット アイテムを設定します。|  
|[CToolBarCtrl::SetImageList](../Topic/CToolBarCtrl::SetImageList.md)|既定の状態のボタンを表示する場合は、ツール バーで使用されるイメージ リストを設定します。|  
|[CToolBarCtrl::SetIndent](../Topic/CToolBarCtrl::SetIndent.md)|ツール バーの最初のボタンのインデントを設定します。|  
|[CToolBarCtrl::SetInsertMark](../Topic/CToolBarCtrl::SetInsertMark.md)|ツール バーの現在の挿入マークを設定します。|  
|[CToolBarCtrl::SetInsertMarkColor](../Topic/CToolBarCtrl::SetInsertMarkColor.md)|色をツール バーの挿入マークの描画に使用する設定します。|  
|[CToolBarCtrl::SetMaxTextRows](../Topic/CToolBarCtrl::SetMaxTextRows.md)|ツール バー ボタンに表示されるテキストの行の最大数を設定します。|  
|[CToolBarCtrl::SetMetrics](../Topic/CToolBarCtrl::SetMetrics.md)|ツール バー コントロールのメトリックを設定します。|  
|[CToolBarCtrl::SetOwner](../Topic/CToolBarCtrl::SetOwner.md)|ウィンドウのツール バー コントロールからの通知メッセージを受信するに設定します。|  
|[CToolBarCtrl::SetPadding](../Topic/CToolBarCtrl::SetPadding.md)|現在のツール バー コントロールの水平方向と垂直方向の埋め込みを設定します。|  
|[CToolBarCtrl::SetPressedImageList](../Topic/CToolBarCtrl::SetPressedImageList.md)|押された状態のボタンを表すために現在のツール バー コントロールが使用するイメージ リストを設定します。|  
|[CToolBarCtrl::SetRows](../Topic/CToolBarCtrl::SetRows.md)|ツール バーに表示されるボタン列数を設定します。|  
|[CToolBarCtrl::SetState](../Topic/CToolBarCtrl::SetState.md)|ツール バーの指定コントロール ボタンの状態を設定します。|  
|[CToolBarCtrl::SetStyle](../Topic/CToolBarCtrl::SetStyle.md)|ツール バー コントロールのスタイルを設定します。|  
|[CToolBarCtrl::SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md)|ツール バー コントロールでツール ヒント コントロールに関連付けます。|  
|[CToolBarCtrl::SetWindowTheme](../Topic/CToolBarCtrl::SetWindowTheme.md)|ツール バー コントロールでの視覚スタイルを設定します。|  
  
## 解説  
 このコントロール \(したがって `CToolBarCtrl` のクラス\) \/98 Windows 95 および Windows NT 3.51 以降で実行されるプログラムにのみ使用できます。  
  
 Windows ツール バー コモン コントロールは、一つ以上のボタンを含む四角形の子ウィンドウです。  これらのボタンは、ビットマップ イメージ、または両方を表示できます。  ユーザーがボタンをクリックした場合、ツール バーのオーナー ウィンドウにコマンド メッセージを送信します。  通常、ツール バー ボタンはアプリケーションのメニュー項目に対応します; これらは、ユーザーが直接の方法をアプリケーションのコマンド アクセスを提供します。  
  
 `CToolBarCtrl` のオブジェクトは、いくつかの重要な内部のデータ構造体が含まれています: ボタンのイメージのビットマップ イメージのリストまたはリスト、ボタンのラベル文字列のリスト、および位置と文字列を、イメージやスタイルを示す作ったり、関連付ける `TBBUTTON` の構造体のリストは、ボタンのコマンド ID。  これらのデータ構造体の各要素には、から始まるインデックスで参照されます。  `CToolBarCtrl` のオブジェクトを使用する前に、これらのデータ構造を設定する必要があります。  文字列のリストはボタンのラベルにしか使用できません; ツール バーから文字列を取得できません。  
  
 `CToolBarCtrl` のオブジェクトを使用するには、通常、次の手順を実行します:  
  
1.  `CToolBarCtrl` オブジェクトを構築します。  
  
2.  Windows ツール バー コモン コントロールを作成し、`CToolBarCtrl` のオブジェクトにアタッチするに [&#91;作成&#93;](../Topic/CToolBarCtrl::Create.md) を呼び出します。  透明なツール バーに **TBSTYLE\_TRANSPARENT** またはツール バーに **TBSTYLE\_DROPDOWN** のようなスタイルを使用してツール バー スタイルをサポートするドロップダウン スタイルのボタンという名前を付けます。  
  
3.  表示するツール バー ボタンがする方法を識別する:  
  
    -   ボタンのビットマップ イメージを使用するには、[AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md)を呼び出して、ツール バーにボタンのビットマップを追加します。  
  
    -   イメージ リストから表示されるボタンのイメージを使用するには、[SetImageList](../Topic/CToolBarCtrl::SetImageList.md)、[SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md)、または [SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md)を呼び出してイメージ リストを指定します。  
  
    -   ボタンの文字列のラベルを使用するには、[AddString](../Topic/CToolBarCtrl::AddString.md) や [AddStrings](../Topic/CToolBarCtrl::AddStrings.md)を呼び出して、ツール バーに文字列を追加します。  
  
4.  [AddButtons](../Topic/CToolBarCtrl::AddButtons.md)を呼び出して、ツール バーにボタンの構造を追加します。  
  
5.  `CFrameWnd`ではないオーナー ウィンドウのツール バーのボタンのツール ヒントが必要な場合は、[ツール ヒントの通知の処理](../../mfc/handling-tool-tip-notifications.md)に説明されているように、ツール バーのオーナー ウィンドウの **TTN\_NEEDTEXT** のメッセージを処理する必要があります。  ツール バーの親ウィンドウが `CFrameWnd`から派生している場合、ツール ヒントは、からの際の作業を行わずに `CFrameWnd` が既定のハンドラーを提供するため表示されます。  
  
6.  ユーザーにツール バーをカスタマイズする場合は、[カスタマイズの通知の処理](../Topic/Handling%20Customization%20Notifications.md)に説明されているように、オーナー ウィンドウのカスタマイズの通知メッセージを処理します。  
  
 レジストリに格納されている情報に基づいて状態を復元するためにレジストリと [RestoreState](../Topic/CToolBarCtrl::RestoreState.md) ツール バー コントロールの現在の状態を保存するために [SaveState](../Topic/CToolBarCtrl::SaveState.md) を使用できます。  アプリケーションのどちらのツール バーの状態を保存することに加えて、アプリケーションでは、通常、ユーザーが後にツール バーを元の状態に復元するには、ユーザーがツール バーをカスタマイズを開始する前に状態を格納します。  
  
## Internet Explorer Version 4.0 のサポート以降  
 Internet Explorer で、バージョン 4.0 以降で導入されたツール バー コントロールにサポートするには、の機能を MFC イメージ リストのサポートと透明に、フラット スタイルを指定します。  
  
 透過的なツール バーの下でクライアントが示すことができます。  透明なツール バーを作成するには、**TBSTYLE\_FLAT** との両方 **TBSTYLE\_TRANSPARENT** スタイルを使用します。  透明なツール バー、ホット トラッキングが使用されています; つまり、マウス ポインターがツール バーのホット ボタンの上に移動すると、ボタンの外観は変化します。  、**TBSTYLE\_FLAT** のスタイルで作成されたツール バーは透過的でないボタンがあります。  
  
 イメージ リストのサポートは、コントロールの既定の動作、ホット イメージと無効イメージの柔軟性を提供します。  状態に従ってイメージの処理に透明なツール バーの [GetImageList](../Topic/CToolBarCtrl::GetImageList.md)、[GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md)と [GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md) の使用:  
  
 `CToolBarCtrl`の使用の詳細については、[コントロール](../../mfc/controls-mfc.md) と [を使用して CToolBarCtrl](../../mfc/using-ctoolbarctrl.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CToolBarCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [MFC CMNCTRL1 サンプル](../../top/visual-cpp-samples.md)   
 [MFC MFCIE サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBar クラス](../../mfc/reference/ctoolbar-class.md)