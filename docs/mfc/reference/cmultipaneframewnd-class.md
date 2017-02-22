---
title: "CMultiPaneFrameWnd クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMultiPaneFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPaneFrameWnd クラス"
ms.assetid: 989a548e-0d70-46b7-a513-8cf740e1be3e
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMultiPaneFrameWnd クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMultiPaneFrameWnd` クラスは、[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md) を拡張します。  複数のペインをサポートします。  `CMultiPaneFrameWnd` には、コントロール バーへの単一のハンドルが埋め込まれる代わりに、[CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md) オブジェクトが格納されます。このオブジェクトにより、1 つの `CMultiPaneFrameWnd` を別のウィンドウにドッキングしたり、複数のフローティング状態のタブ付きウィンドウを動的に作成したりできるようになります。  
  
## 構文  
  
```  
class CMultiPaneFrameWnd : public CPaneFrameWnd  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMultiPaneFrameWnd::AddPane](../Topic/CMultiPaneFrameWnd::AddPane.md)|ペインを追加します。  \([CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::AddRecentPane](../Topic/CMultiPaneFrameWnd::AddRecentPane.md)||  
|[CMultiPaneFrameWnd::AdjustLayout](../Topic/CMultiPaneFrameWnd::AdjustLayout.md)|ミニフレーム ウィンドウのレイアウトを調整します。  \([CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::AdjustPaneFrames](../Topic/CMultiPaneFrameWnd::AdjustPaneFrames.md)|\([CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md) をオーバーライドします。\)|  
|[CMultiPaneFrameWnd::CalcExpectedDockedRect](../Topic/CMultiPaneFrameWnd::CalcExpectedDockedRect.md)|ドッキング ウィンドウの予想される四角形を計算します   \([CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::CanBeAttached](../Topic/CMultiPaneFrameWnd::CanBeAttached.md)|現在のペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを判定します   \([CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::CanBeDockedToPane](../Topic/CMultiPaneFrameWnd::CanBeDockedToPane.md)|ミニフレーム ウィンドウをペインにドッキングできるかどうかを判定します   \([CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::CheckGripperVisibility](../Topic/CMultiPaneFrameWnd::CheckGripperVisibility.md)|\([CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md) をオーバーライドします。\)|  
|[CMultiPaneFrameWnd::CloseMiniFrame](../Topic/CMultiPaneFrameWnd::CloseMiniFrame.md)|\(`CPaneFrameWnd::CloseMiniFrame` をオーバーライドします。\)|  
|[CMultiPaneFrameWnd::ConvertToTabbedDocument](../Topic/CMultiPaneFrameWnd::ConvertToTabbedDocument.md)|ペインをタブ付きドキュメントに変換します。  \([CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::DockFrame](../Topic/CMultiPaneFrameWnd::DockFrame.md)||  
|[CMultiPaneFrameWnd::DockPane](../Topic/CMultiPaneFrameWnd::DockPane.md)|ペインをドッキングします。  \([CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::DockRecentPaneToMainFrame](../Topic/CMultiPaneFrameWnd::DockRecentPaneToMainFrame.md)||  
|[CMultiPaneFrameWnd::GetCaptionText](../Topic/CMultiPaneFrameWnd::GetCaptionText.md)|キャプション テキストを返します。  \([CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::GetPaneContainerManager](../Topic/CMultiPaneFrameWnd::GetPaneContainerManager.md)|内部コンテナー マネージャー オブジェクトへの参照を返します。|  
|[CMultiPaneFrameWnd::GetFirstVisiblePane](../Topic/CMultiPaneFrameWnd::GetFirstVisiblePane.md)|ミニフレーム ウィンドウに含まれる、最初の可視ペインを返します。  \([CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::GetPane](../Topic/CMultiPaneFrameWnd::GetPane.md)|ミニフレーム ウィンドウに含まれているペインを返します。  \([CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::GetPaneCount](../Topic/CMultiPaneFrameWnd::GetPaneCount.md)|ミニフレーム ウィンドウに含まれているペインの数を返します。  \([CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::GetVisiblePaneCount](../Topic/CMultiPaneFrameWnd::GetVisiblePaneCount.md)|ミニフレーム ウィンドウに含まれている可視ペインの数を返します。  \([CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::InsertPane](../Topic/CMultiPaneFrameWnd::InsertPane.md)||  
|[CMultiPaneFrameWnd::LoadState](../Topic/CMultiPaneFrameWnd::LoadState.md)|レジストリからペインの状態を読み込みます。  \([CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::OnDockToRecentPos](../Topic/CMultiPaneFrameWnd::OnDockToRecentPos.md)|ミニフレーム ウィンドウを直前の位置にドッキングします。  \([CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::OnKillRollUpTimer](../Topic/CMultiPaneFrameWnd::OnKillRollUpTimer.md)|ロールアップ タイマーを停止します。  \([CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::OnPaneRecalcLayout](../Topic/CMultiPaneFrameWnd::OnPaneRecalcLayout.md)|ミニフレーム ウィンドウ内のペインのレイアウトを調整します   \([CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::OnSetRollUpTimer](../Topic/CMultiPaneFrameWnd::OnSetRollUpTimer.md)|ロールアップ タイマーを設定します。  \([CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::OnShowPane](../Topic/CMultiPaneFrameWnd::OnShowPane.md)|ミニフレーム ウィンドウのペインが表示されるとき、または非表示になるときに、フレームワークによって呼び出されます。  \([CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::PaneFromPoint](../Topic/CMultiPaneFrameWnd::PaneFromPoint.md)|ユーザーが指定した位置がミニフレーム ウィンドウ内のペインに含まれている場合、そのペインを返します。  \([CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::RemoveNonValidPanes](../Topic/CMultiPaneFrameWnd::RemoveNonValidPanes.md)|有効でないペインを削除するために、フレームワークによって呼び出されます。  \([CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::RemovePane](../Topic/CMultiPaneFrameWnd::RemovePane.md)|ミニフレーム ウィンドウからペインを削除します。  \([CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::ReplacePane](../Topic/CMultiPaneFrameWnd::ReplacePane.md)|ペインを別のペインに置き換えます。  \([CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::SaveState](../Topic/CMultiPaneFrameWnd::SaveState.md)|レジストリにペインの状態を保存します。  \([CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::Serialize](../Topic/CMultiPaneFrameWnd::Serialize.md)|\(`CPaneFrameWnd::Serialize` をオーバーライドします。\)|  
|[CMultiPaneFrameWnd::SetDockState](../Topic/CMultiPaneFrameWnd::SetDockState.md)|ドッキング状態を設定します。  \([CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::SetLastFocusedPane](../Topic/CMultiPaneFrameWnd::SetLastFocusedPane.md)||  
|[CMultiPaneFrameWnd::SetPreDockState](../Topic/CMultiPaneFrameWnd::SetPreDockState.md)|ドッキング前の状態を設定します   \([CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md) をオーバーライドします\)。|  
|[CMultiPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CMultiPaneFrameWnd::StoreRecentDockSiteInfo.md)|\([CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md) をオーバーライドします。\)|  
|[CMultiPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CMultiPaneFrameWnd::StoreRecentTabRelatedInfo.md)|\([CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md) をオーバーライドします。\)|  
  
## 解説  
 このクラスのほとんどのメソッドは、[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md) のメソッドをオーバーライドします。  
  
 ペインが `AFX_CBRS_AUTO_ROLLUP` スタイルを使用し、ユーザーがそのペインをマルチペイン フレーム ウィンドウにドッキングする場合、ドッキングされた他のペインのスタイル設定に関係なく、ユーザーはウィンドウをロールアップできます。  
  
 ユーザーが `CBRS_FLOAT_MULTI` スタイルを使用するペインをフローティング状態にする場合、フレームワークは自動的に `CMultiPaneFrameWnd` オブジェクトを作成します。  
  
 `CPaneFrameWnd` クラスからクラスを派生させ、それを動的に作成することに関する詳細については、「[CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)」を参照してください。  
  
## 使用例  
 `CMultiPaneFrameWnd` オブジェクトへのポインターを取得する方法を次の例に示します。  このコード スニペットは [ウィンドウのサイズのサンプルを設定します。](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_SetPaneSize#4](../../mfc/reference/codesnippet/CPP/cmultipaneframewnd-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
 [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)  
  
## 必要条件  
 **ヘッダー :** afxMultiPaneFrameWnd.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)