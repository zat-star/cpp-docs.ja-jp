---
title: "CMFCToolBarMenuButton クラス | Microsoft Docs"
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
  - "CMFCToolBarMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarMenuButton クラス"
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: 31
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarMenuButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ポップアップ メニューを含むツール バー ボタンです。  
  
## 構文  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](../Topic/CMFCToolBarMenuButton::CMFCToolBarMenuButton.md)|`CMFCToolBarMenuButton` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarMenuButton::CompareWith](../Topic/CMFCToolBarMenuButton::CompareWith.md)|指定された `CMFCToolBarButton` オブジェクトを、このインスタンスと比較します。  \([CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::CopyFrom](../Topic/CMFCToolBarMenuButton::CopyFrom.md)|別のツール バー ボタンのプロパティを現在のボタンにコピーします。  \([CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::CreateFromMenu](../Topic/CMFCToolBarMenuButton::CreateFromMenu.md)|Windows メニュー ハンドルからツール バー メニューを初期化します。|  
|[CMFCToolBarMenuButton::CreateMenu](../Topic/CMFCToolBarMenuButton::CreateMenu.md)|ツール バー メニューのコマンドで構成される Windows メニューを作成します。  Windows メニューを識別するハンドルを返します。|  
|[CMFCToolBarMenuButton::CreatePopupMenu](../Topic/CMFCToolBarMenuButton::CreatePopupMenu.md)|ツール バー メニューを表示するために、ポップアップ メニュー オブジェクト \([CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md)\) を作成します。|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](../Topic/CMFCToolBarMenuButton::EnableQuickCustomize.md)||  
|[CMFCToolBarMenuButton::GetCommands](../Topic/CMFCToolBarMenuButton::GetCommands.md)|ツール バー メニューのコマンドのリストへの、読み取り専用アクセスを提供します。|  
|[CMFCToolBarMenuButton::GetImageRect](../Topic/CMFCToolBarMenuButton::GetImageRect.md)|ボタン イメージに外接する四角形を取得します。|  
|[CMFCToolBarMenuButton::GetPaletteRows](../Topic/CMFCToolBarMenuButton::GetPaletteRows.md)|メニューがパレット モードの場合にポップアップ メニューの行数を返します。|  
|[CMFCToolBarMenuButton::GetPopupMenu](../Topic/CMFCToolBarMenuButton::GetPopupMenu.md)|ボタンに関連付けられたポップアップ メニュー オブジェクトへのポインターを返します。|  
|[CMFCToolBarMenuButton::HasButton](../Topic/CMFCToolBarMenuButton::HasButton.md)||  
|[CMFCToolBarMenuButton::HaveHotBorder](../Topic/CMFCToolBarMenuButton::HaveHotBorder.md)|ユーザーがボタンを選択したときに、ボタンの境界線を表示するかどうかを判定します   \([CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::IsBorder](../Topic/CMFCToolBarMenuButton::IsBorder.md)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](../Topic/CMFCToolBarMenuButton::IsClickedOnMenu.md)||  
|[CMFCToolBarMenuButton::IsDroppedDown](../Topic/CMFCToolBarMenuButton::IsDroppedDown.md)|ポップアップ メニューを表示するかどうかを判断します。|  
|[CMFCToolBarMenuButton::IsEmptyMenuAllowed](../Topic/CMFCToolBarMenuButton::IsEmptyMenuAllowed.md)|ユーザーが選択したメニュー項目のサブメニューを開くことができるかどうかを判断するために、フレームワークによって呼び出されます。|  
|[CMFCToolBarMenuButton::IsExclusive](../Topic/CMFCToolBarMenuButton::IsExclusive.md)|ボタンが排他モードかどうか、つまり、ユーザーが別のツール バーまたはボタンの上にポインターを移動しても、ポップアップ メニューが開かれたままであるかどうかを判断します。|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](../Topic/CMFCToolBarMenuButton::IsMenuPaletteMode.md)|ポップアップ メニューがパレット モードかどうかを判断します。|  
|[CMFCToolBarMenuButton::IsQuickMode](../Topic/CMFCToolBarMenuButton::IsQuickMode.md)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](../Topic/CMFCToolBarMenuButton::IsTearOffMenu.md)|ポップアップ メニューにティアオフ バーがあるかどうかを判断します。|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](../Topic/CMFCToolBarMenuButton::OnAfterCreatePopupMenu.md)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](../Topic/CMFCToolBarMenuButton::OnBeforeDrag.md)|ボタンをドラッグできるかどうかを指定します。  \([CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::OnCalculateSize](../Topic/CMFCToolBarMenuButton::OnCalculateSize.md)|指定されたデバイス コンテキストとドッキングの状態に応じたボタンのサイズを計算するために、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::OnCancelMode](../Topic/CMFCToolBarMenuButton::OnCancelMode.md)|[WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) メッセージを処理するために、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](../Topic/CMFCToolBarMenuButton::OnChangeParentWnd.md)|新しいツール バーにボタンが挿入されたときに、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md) をオーバーライドします\)。|  
|[CMFCToolBarMenuButton::OnClick](../Topic/CMFCToolBarMenuButton::OnClick.md)|ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::OnClickMenuItem](../Topic/CMFCToolBarMenuButton::OnClickMenuItem.md)|ユーザーがポップアップ メニュー内の項目を選択すると、フレームワークによって呼び出されます。|  
|[CMFCToolBarMenuButton::OnContextHelp](../Topic/CMFCToolBarMenuButton::OnContextHelp.md)|親ツール バーが `WM_HELPHITTEST` メッセージを処理するときに、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::OnDraw](../Topic/CMFCToolBarMenuButton::OnDraw.md)|指定されたスタイルとオプションを使用してボタンを描画するために、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarMenuButton::OnDrawOnCustomizeList.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[コマンド\]** ペインにボタンを描画するために、フレームワークによって呼び出されます。  \([CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::OpenPopupMenu](../Topic/CMFCToolBarMenuButton::OpenPopupMenu.md)|ユーザーがポップアップ メニューを開くと、フレームワークによって呼び出されます。|  
|[CMFCToolBarMenuButton::ResetImageToDefault](../Topic/CMFCToolBarMenuButton::ResetImageToDefault.md)|ボタンに関連付けられるイメージに既定の値を設定します。  \([CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::SaveBarState](../Topic/CMFCToolBarMenuButton::SaveBarState.md)|ツール バー ボタンの状態を保存します。  \([CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::Serialize](../Topic/CMFCToolBarMenuButton::Serialize.md)|このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます   \([CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::SetACCData](../Topic/CMFCToolBarMenuButton::SetACCData.md)|指定された `CAccessibilityData` オブジェクトに、ツール バー ボタンのアクセシビリティ データを設定します。  \([CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md) をオーバーライドします。\)|  
|[CMFCToolBarMenuButton::SetMenuOnly](../Topic/CMFCToolBarMenuButton::SetMenuOnly.md)|ボタンをツール バーに追加できるかどうかを指定します。|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](../Topic/CMFCToolBarMenuButton::SetMenuPaletteMode.md)|ポップアップ メニューがパレット モードかどうかを指定します。|  
|[CMFCToolBarMenuButton::SetMessageWnd](../Topic/CMFCToolBarMenuButton::SetMessageWnd.md)||  
|[CMFCToolBarMenuButton::SetRadio](../Topic/CMFCToolBarMenuButton::SetRadio.md)|ツール バー メニュー ボタンに、そのボタンが選択されていることを示すアイコンを強制的に表示します。|  
|[CMFCToolBarMenuButton::SetTearOff](../Topic/CMFCToolBarMenuButton::SetTearOff.md)|ポップアップ メニューのティアオフ バー ID を指定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](../Topic/CMFCToolBarMenuButton::DrawDocumentIcon.md)|メニュー ボタンにアイコンを描画します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarMenuButton::m\_bAlwaysCallOwnerDraw](../Topic/CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw.md)|`TRUE` の場合は、ボタンが描画されると必ず、フレームワークが [CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md) を呼び出します。|  
  
## 解説  
 `CMFCToolBarMenuButton` は、メニュー、サブメニューのあるメニュー項目、コマンドを実行するかメニューを表示するボタン、またはメニューだけを表示するボタンとして表示されます。  メニュー ボタンの動作や外観を決定するには、イメージ、テキスト、メニュー ハンドル、コンストラクター `CMFCToolbarMenuButton::CMFCToolbarMenuButton` のボタンに関連付けられているコマンド ID などのパラメーターを指定します。  
  
 `CMFCToolbarMenuButton` クラスから派生したカスタム クラスでは、[DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) マクロを使用する必要があります。  [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) マクロは、アプリケーションが終了するときにエラーを生成します。  
  
## 使用例  
 `CMFCToolBarMenuButton` オブジェクトを構成する方法を次の例に示します。  このコードは、ドロップダウン メニューがパレット モードかどうかを指定する方法、およびユーザーがメニュー ボタンをメニュー バーの外にドラッグしたときに作成されるティアオフ バーの ID を指定する方法を示しています。  このコード スニペットは [Word のスペースのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#10](../../mfc/reference/codesnippet/CPP/cmfctoolbarmenubutton-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
## 必要条件  
 **ヘッダー :** afxtoolbarmenubutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md)