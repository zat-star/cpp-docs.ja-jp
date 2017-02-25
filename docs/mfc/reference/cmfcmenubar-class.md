---
title: "CMFCMenuBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMenuBar クラス"
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMFCMenuBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ドッキングを実装するメニュー バーです。  
  
## 構文  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCMenuBar::AdjustLocations](../Topic/CMFCMenuBar::AdjustLocations.md)|\(`CMFCToolBar::AdjustLocations` をオーバーライドします。\)|  
|[CMFCMenuBar::AllowChangeTextLabels](../Topic/CMFCMenuBar::AllowChangeTextLabels.md)|ツール バー ボタンのイメージの下にテキスト ラベルを表示できるかどうかを示します   \([CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md) をオーバーライドします\)。|  
|[CMFCMenuBar::AllowShowOnPaneMenu](../Topic/CMFCMenuBar::AllowShowOnPaneMenu.md)|\(`CPane::AllowShowOnPaneMenu` をオーバーライドします。\)|  
|[CMFCMenuBar::CalcFixedLayout](../Topic/CMFCMenuBar::CalcFixedLayout.md)|ツール バーの水平サイズを計算します。  \([CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md) をオーバーライドします\)。|  
|[CMFCMenuBar::CalcLayout](../Topic/CMFCMenuBar::CalcLayout.md)|\(`CMFCToolBar::CalcLayout` をオーバーライドします。\)|  
|[CMFCMenuBar::CalcMaxButtonHeight](../Topic/CMFCMenuBar::CalcMaxButtonHeight.md)|ツール バーのボタンの高さの最大値を計算します。  \([CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md) をオーバーライドします\)。|  
|[CMFCMenuBar::CanBeClosed](../Topic/CMFCMenuBar::CanBeClosed.md)|ユーザーがツール バーを閉じることができるかどうかを示します。  \([CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md) をオーバーライドします\)。|  
|[CMFCMenuBar::CanBeRestored](../Topic/CMFCMenuBar::CanBeRestored.md)|カスタマイズ後にツール バーを元の状態に復元できるかどうかを判断します。  \([CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md) をオーバーライドします\)。|  
|[CMFCMenuBar::Create](../Topic/CMFCMenuBar::Create.md)|メニュー コントロールを作成し、`CMFCMenuBar` オブジェクトにアタッチします。|  
|[CMFCMenuBar::CreateEx](../Topic/CMFCMenuBar::CreateEx.md)|`CMFCMenuBar` オブジェクトを作成します。追加のスタイル オプションを指定します。|  
|[CMFCMenuBar::CreateFromMenu](../Topic/CMFCMenuBar::CreateFromMenu.md)|`CMFCMenuBar` オブジェクトを初期化します。  取得された `CMFCMenuBar` のテンプレートとして動作する `HMENU` パラメーターを受け入れます。|  
|[CMFCMenuBar::EnableHelpCombobox](../Topic/CMFCMenuBar::EnableHelpCombobox.md)|メニュー バーの右側にある **\[Help\]** ボックスを有効にします。|  
|[CMFCMenuBar::EnableMenuShadows](../Topic/CMFCMenuBar::EnableMenuShadows.md)|ポップアップ メニューの影を表示するかどうかを指定します。|  
|[CMFCMenuBar::GetAvailableExpandSize](../Topic/CMFCMenuBar::GetAvailableExpandSize.md)|\([CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md) をオーバーライドします。\)|  
|[CMFCMenuBar::GetColumnWidth](../Topic/CMFCMenuBar::GetColumnWidth.md)|ツール バー ボタンの幅を返します。  \([CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md) をオーバーライドします\)。|  
|[CMFCMenuBar::GetDefaultMenu](../Topic/CMFCMenuBar::GetDefaultMenu.md)|リソース ファイルでの元のメニューのハンドルを返します。|  
|[CMFCMenuBar::GetDefaultMenuResId](../Topic/CMFCMenuBar::GetDefaultMenuResId.md)|リソース ファイルでの元のメニューのリソース識別子を返します。|  
|[CMFCMenuBar::GetFloatPopupDirection](../Topic/CMFCMenuBar::GetFloatPopupDirection.md)||  
|[CMFCMenuBar::GetForceDownArrows](../Topic/CMFCMenuBar::GetForceDownArrows.md)||  
|[CMFCMenuBar::GetHelpCombobox](../Topic/CMFCMenuBar::GetHelpCombobox.md)|**\[ヘルプ\]** ボックスへのポインターを返します。|  
|[CMFCMenuBar::GetHMenu](../Topic/CMFCMenuBar::GetHMenu.md)|`CMFCMenuBar` オブジェクトにアタッチされているメニューのハンドルを返します。|  
|[CMFCMenuBar::GetMenuFont](../Topic/CMFCMenuBar::GetMenuFont.md)|メニュー オブジェクトの現在のグローバル フォントを返します。|  
|[CMFCMenuBar::GetMenuItem](../Topic/CMFCMenuBar::GetMenuItem.md)|指定された項目のインデックスに関連付けられたツール バー ボタンを返します。|  
|[CMFCMenuBar::GetRowHeight](../Topic/CMFCMenuBar::GetRowHeight.md)|ツール バー ボタンの高さを返します。  \([CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md) をオーバーライドします\)。|  
|[CMFCMenuBar::GetSystemButton](../Topic/CMFCMenuBar::GetSystemButton.md)||  
|[CMFCMenuBar::GetSystemButtonsCount](../Topic/CMFCMenuBar::GetSystemButtonsCount.md)||  
|[CMFCMenuBar::GetSystemMenu](../Topic/CMFCMenuBar::GetSystemMenu.md)||  
|[CMFCMenuBar::HighlightDisabledItems](../Topic/CMFCMenuBar::HighlightDisabledItems.md)|無効なメニュー項目を強調表示するかどうかを示します。|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](../Topic/CMFCMenuBar::IsButtonExtraSizeAvailable.md)|拡張された境界を持つボタンをツール バーが表示できるかどうかを判断します   \([CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md) をオーバーライドします\)。|  
|[CMFCMenuBar::IsHighlightDisabledItems](../Topic/CMFCMenuBar::IsHighlightDisabledItems.md)|無効な項目を強調表示するかどうかを指定します。|  
|[CMFCMenuBar::IsMenuShadows](../Topic/CMFCMenuBar::IsMenuShadows.md)|ポップアップ メニューの影を描画するかどうかを指定します。|  
|[CMFCMenuBar::IsRecentlyUsedMenus](../Topic/CMFCMenuBar::IsRecentlyUsedMenus.md)|最近使用したメニュー コマンドがメニュー バーに表示されているかどうかを示します。|  
|[CMFCMenuBar::IsShowAllCommands](../Topic/CMFCMenuBar::IsShowAllCommands.md)|ポップアップ メニューにすべてのコマンドを表示するかどうかを指定します。|  
|[CMFCMenuBar::IsShowAllCommandsDelay](../Topic/CMFCMenuBar::IsShowAllCommandsDelay.md)|少し時間が経つとメニューにすべてのコマンドを表示するかどうかを指定します。|  
|[CMFCMenuBar::LoadState](../Topic/CMFCMenuBar::LoadState.md)|レジストリから `CMFCMenuBar` オブジェクトの状態を読み込みます。|  
|[CMFCMenuBar::OnChangeHot](../Topic/CMFCMenuBar::OnChangeHot.md)|ツール バー上のボタンが選択されたときに、フレームワークによって呼び出されます。  \([CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md) をオーバーライドします\)。|  
|[CMFCMenuBar::OnDefaultMenuLoaded](../Topic/CMFCMenuBar::OnDefaultMenuLoaded.md)|フレーム ウィンドウがリソース ファイルから既定のメニューを読み込んだときに、フレームワークによって呼び出されます。|  
|[CMFCMenuBar::OnSendCommand](../Topic/CMFCMenuBar::OnSendCommand.md)|\(`CMFCToolBar::OnSendCommand` をオーバーライドします。\)|  
|[CMFCMenuBar::OnSetDefaultButtonText](../Topic/CMFCMenuBar::OnSetDefaultButtonText.md)|メニューがカスタマイズ モードで、ユーザーがメニュー項目のテキストを変更したときに、フレームワークによって呼び出されます。|  
|[CMFCMenuBar::OnToolHitTest](../Topic/CMFCMenuBar::OnToolHitTest.md)|\(`CMFCToolBar::OnToolHitTest` をオーバーライドします。\)|  
|[CMFCMenuBar::PreTranslateMessage](../Topic/CMFCMenuBar::PreTranslateMessage.md)|\(`CMFCToolBar::PreTranslateMessage` をオーバーライドします。\)|  
|[CMFCMenuBar::RestoreOriginalstate](../Topic/CMFCMenuBar::RestoreOriginalstate.md)|メニューがカスタマイズ モードで、ユーザーがメニュー バーの **\[リセット\]** をクリックしたときに、フレームワークによって呼び出されます。|  
|[CMFCMenuBar::SaveState](../Topic/CMFCMenuBar::SaveState.md)|`CMFCMenuBar` オブジェクトの状態をレジストリに保存します。|  
|[CMFCMenuBar::SetDefaultMenuResId](../Topic/CMFCMenuBar::SetDefaultMenuResId.md)|リソース ファイルに元のメニューを設定します。|  
|[CMFCMenuBar::SetForceDownArrows](../Topic/CMFCMenuBar::SetForceDownArrows.md)||  
|[CMFCMenuBar::SetMaximizeMode](../Topic/CMFCMenuBar::SetMaximizeMode.md)|MDI 子ウィンドウの表示モードが変更されたときに、フレームワークによって呼び出されます。  MDI 子ウィンドウが新たに最大化されるか、それ以上最大化できない場合、このメソッドはメニュー バーを更新します。|  
|[CMFCMenuBar::SetMenuButtonRTC](../Topic/CMFCMenuBar::SetMenuButtonRTC.md)|ユーザーがメニュー ボタンを動的に作成するときに生成されるランタイム クラス情報を設定します。|  
|[CMFCMenuBar::SetMenuFont](../Topic/CMFCMenuBar::SetMenuFont.md)|アプリケーション内のすべてのメニューのフォントを設定します。|  
|[CMFCMenuBar::SetRecentlyUsedMenus](../Topic/CMFCMenuBar::SetRecentlyUsedMenus.md)|最近使用したメニュー コマンドをメニュー バーに表示するかどうかを指定します。|  
|[CMFCMenuBar::SetShowAllCommands](../Topic/CMFCMenuBar::SetShowAllCommands.md)|メニュー バーにすべてのコマンドを表示するかどうかを指定します。|  
  
## 解説  
 `CMFCMenuBar` クラスは、ドッキング機能を実装するメニュー バーです。  これはツール バーに似ています。ただし、閉じることはできません \(常に表示されています\)。  
  
 `CMFCMenuBar` は、最近使用されたメニュー項目オブジェクトを表示するオプションをサポートします。  このオプションが有効な場合、`CMFCMenuBar` は、使用できるコマンドのサブセットのみを最初の画面に表示します。  その後、最近使用されたコマンドが元のコマンドのサブセットと一緒に表示されます。  また、ユーザーはいつでもメニューを拡張して、使用できるすべてのコマンドを表示できます。  したがって、使用できる各コマンドに対して、常に表示するか、最近使用された場合のみ表示するかを設定します。  
  
 `CMFCMenuBar` オブジェクトを使用するには、これをメイン ウィンドウ フレーム オブジェクトに埋め込みます。  `WM_CREATE` メッセージを処理する場合は、`CMFCMenuBar::Create` または `CMFCMenuBar::CreateEx` を呼び出します。  使用する作成関数に関係なくメイン フレーム ウィンドウへのポインターに渡されます。  次に、[CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md) を呼び出してドッキングを有効にします。  [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md) を呼び出して、このメニューをドッキングします。  
  
## 使用例  
 次の例は、`CMFCMenuBar` クラスのさまざまなメソッドの使用方法を説明しています。  例では、ペインのスタイルの設定、カスタマイズ ボタンの有効化、\[ヘルプ\] ボックスの有効化、ポップアップ メニューの影の有効化、およびメニュー バーの更新について、その方法を説明しています。  このコード スニペットは [IE のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/CPP/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/CPP/cmfcmenubar-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxmenubar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)