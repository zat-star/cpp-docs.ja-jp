---
title: "CMFCPopupMenuBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPopupMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPopupMenuBar クラス"
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# CMFCPopupMenuBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ポップアップ メニューに埋め込まれたメニュー バーです。  
  
## 構文  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](../Topic/CMFCPopupMenuBar::AdjustSizeImmediate.md)|ペインのレイアウトをすぐに再計算します。  \([CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md) をオーバーライドします\)。|  
|[CMFCPopupMenuBar::BuildOrigItems](../Topic/CMFCPopupMenuBar::BuildOrigItems.md)|指定されたメニュー リソースのポップアップ メニュー項目を読み込みます。|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](../Topic/CMFCPopupMenuBar::CloseDelayedSubMenu.md)|遅延ポップアップ メニュー ボタンを閉じます。|  
|[CMFCPopupMenuBar::ExportToMenu](../Topic/CMFCPopupMenuBar::ExportToMenu.md)|ポップアップ メニュー ボタンのメニューをビルドします。|  
|[CMFCPopupMenuBar::FindDestintationToolBar](../Topic/CMFCPopupMenuBar::FindDestintationToolBar.md)|指定した点が含まれるツール バーを配置します。|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](../Topic/CMFCPopupMenuBar::GetCurrentMenuImageSize.md)|メニュー ボタンのイメージのサイズを示します。|  
|[CMFCPopupMenuBar::GetDefaultMenuId](../Topic/CMFCPopupMenuBar::GetDefaultMenuId.md)|既定のメニュー項目の識別子を返します。|  
|[CMFCPopupMenuBar::GetLastCommandIndex](../Topic/CMFCPopupMenuBar::GetLastCommandIndex.md)|起動されたメニュー コマンドのインデックスを最新取得します。|  
|[CMFCPopupMenuBar::GetOffset](../Topic/CMFCPopupMenuBar::GetOffset.md)|ポップアップ メニュー バーの行のオフセットを取得します。|  
|[CMFCPopupMenuBar::ImportFromMenu](../Topic/CMFCPopupMenuBar::ImportFromMenu.md)|指定されたメニューからポップアップ メニュー ボタンをインポートします。|  
|[CMFCPopupMenuBar::IsDropDownListMode](../Topic/CMFCPopupMenuBar::IsDropDownListMode.md)|ポップアップ メニュー バーがドロップダウン リストのモードかどうかを示します。|  
|[CMFCPopupMenuBar::IsPaletteMode](../Topic/CMFCPopupMenuBar::IsPaletteMode.md)|ポップアップ メニュー バーがパレット モードかどうかを示します。|  
|[CMFCPopupMenuBar::IsRibbonPanel](../Topic/CMFCPopupMenuBar::IsRibbonPanel.md)|これがリボン パネル`FALSE` \(既定では\) であるかどうかを示します。|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](../Topic/CMFCPopupMenuBar::IsRibbonPanelInRegularMode.md)|これが通常モード`FALSE` \(既定では\) のリボン パネルであるかどうかを示します。|  
|[CMFCPopupMenuBar::LoadFromHash](../Topic/CMFCPopupMenuBar::LoadFromHash.md)|アーカイブ メニューを読み込みます。|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](../Topic/CMFCPopupMenuBar::RestoreDelayedSubMenu.md)|ポップアップ メニュー バーを閉じるための遅延メニュー ボタンを復元します。|  
|[CMFCPopupMenuBar::SetButtonStyle](../Topic/CMFCPopupMenuBar::SetButtonStyle.md)|特定のインデックスのツール バー ボタンのスタイルを設定します。  \([CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md) をオーバーライドします。\)|  
|[CMFCPopupMenuBar::SetOffset](../Topic/CMFCPopupMenuBar::SetOffset.md)|ポップアップ メニュー バーの行のオフセットを設定します。|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](../Topic/CMFCPopupMenuBar::StartPopupMenuTimer.md)|指定した遅延ポップアップ メニュー ボタンのタイマーを開始します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCPopupMenuBar::m\_bDisableSideBarInXPMode](../Topic/CMFCPopupMenuBar::m_bDisableSideBarInXPMode.md)|アプリケーションで Windows XP の表示形式を使用するときに灰色のサイドバーを表示するかどうかを指定します。|  
  
## 解説  
 `CMFCPopupMenuBar` は [CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md)と同時に作成され、その中に埋め込まれます。  `CMFCPopupMenuBar` は、`CMFCPopupMenu` オブジェクトのクライアント領域全体を占有します。  キーボード入力とマウス入力をサポートします。  さらに、その入力を、`CMFCPopupMenu` およびトップ レベルのフレーム ウィンドウに伝えます。  
  
## 使用例  
 `CMFCPopupMenu` オブジェクトから `CMFCPopupMenuBar` オブジェクトを初期化する方法を次の例に示します。  このコード スニペットは [描画のクライアント サンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/CPP/cmfcpopupmenubar-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxpopupmenubar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md)