---
title: "CPaneFrameWnd クラス | Microsoft Docs"
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
  - "CPaneFrameWnd.Serialize"
  - "CPaneFrameWnd.PreTranslateMessage"
  - "CPaneFrameWnd"
  - "CPaneFrameWnd::Serialize"
  - "PreTranslateMessage"
  - "CPaneFrameWnd::PreTranslateMessage"
  - "Serialize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneFrameWnd クラス"
  - "PreTranslateMessage メソッド"
  - "Serialize メソッド"
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneFrameWnd クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 1 つのペインを含むミニフレーム ウィンドウを実装します。  そのペインは、ウィンドウのクライアント領域になります。  
  
## 構文  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md)|ペインを追加します。|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](../Topic/CPaneFrameWnd::AddRemovePaneFromGlobalList.md)|グローバル リストに対してペインを追加または削除します。|  
|[CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md)|ミニフレーム ウィンドウのレイアウトを調整します。|  
|[CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md)||  
|[CPaneFrameWnd::CalcBorderSize](../Topic/CPaneFrameWnd::CalcBorderSize.md)|ミニフレーム ウィンドウの境界線のサイズを計算します。|  
|[CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md)|ドッキング ウィンドウの予想される四角形を計算します。|  
|[CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md)|現在のペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを判定します。|  
|[CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md)|ミニフレーム ウィンドウをペインにドッキングできるかどうかを判定します。|  
|[CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md)|ペインをタブ付きドキュメントに変換します。|  
|[CPaneFrameWnd::Create](../Topic/CPaneFrameWnd::Create.md)|ミニフレーム ウィンドウを作成し、`CPaneFrameWnd` オブジェクトにアタッチします。|  
|[CPaneFrameWnd::CreateEx](../Topic/CPaneFrameWnd::CreateEx.md)|ミニフレーム ウィンドウを作成し、`CPaneFrameWnd` オブジェクトにアタッチします。|  
|[CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md)|ペインをドッキングします。|  
|[CPaneFrameWnd::FindFloatingPaneByID](../Topic/CPaneFrameWnd::FindFloatingPaneByID.md)|フローティング ペインのグローバル リストで、指定したコントロール ID のペインを検索します。|  
|[CPaneFrameWnd::FrameFromPoint](../Topic/CPaneFrameWnd::FrameFromPoint.md)|ユーザーが指定したポイントを含むミニフレーム ウィンドウを検索します。|  
|[CPaneFrameWnd::GetCaptionHeight](../Topic/CPaneFrameWnd::GetCaptionHeight.md)|ミニフレーム ウィンドウのキャプションの高さを返します。|  
|[CPaneFrameWnd::GetCaptionRect](../Topic/CPaneFrameWnd::GetCaptionRect.md)|ミニフレーム ウィンドウのキャプションに外接する四角形を計算します。|  
|[CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md)|キャプション テキストを返します。|  
|[CPaneFrameWnd::GetDockingManager](../Topic/CPaneFrameWnd::GetDockingManager.md)||  
|[CPaneFrameWnd::GetDockingMode](../Topic/CPaneFrameWnd::GetDockingMode.md)|ドッキングのモードを返します。|  
|[CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md)|ミニフレーム ウィンドウに含まれる最初の可視ペインを返します。|  
|[CPaneFrameWnd::GetHotPoint](../Topic/CPaneFrameWnd::GetHotPoint.md)||  
|[CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md)|ミニフレーム ウィンドウに含まれるペインを返します。|  
|[CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md)|ミニフレーム ウィンドウに含まれるペインの数を返します。|  
|[CPaneFrameWnd::GetParent](../Topic/CPaneFrameWnd::GetParent.md)||  
|[CPaneFrameWnd::GetPinState](../Topic/CPaneFrameWnd::GetPinState.md)||  
|[CPaneFrameWnd::GetRecentFloatingRect](../Topic/CPaneFrameWnd::GetRecentFloatingRect.md)||  
|[CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md)|ミニフレーム ウィンドウに含まれる可視ペインの数を返します。|  
|[CPaneFrameWnd::HitTest](../Topic/CPaneFrameWnd::HitTest.md)|特定のポイントに、ミニフレーム ウィンドウのどの部分があるか判定します。|  
|[CPaneFrameWnd::IsCaptured](../Topic/CPaneFrameWnd::IsCaptured.md)||  
|[CPaneFrameWnd::IsDelayShow](../Topic/CPaneFrameWnd::IsDelayShow.md)||  
|[CPaneFrameWnd::IsRollDown](../Topic/CPaneFrameWnd::IsRollDown.md)|ミニフレーム ウィンドウをロール ダウンするかどうかを判断します。|  
|[CPaneFrameWnd::IsRollUp](../Topic/CPaneFrameWnd::IsRollUp.md)|ミニフレーム ウィンドウをロール アップするかどうかを判断します。|  
|[CPaneFrameWnd::KillDockingTimer](../Topic/CPaneFrameWnd::KillDockingTimer.md)|ドッキング タイマーを停止します。|  
|[CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md)|レジストリからペインの状態を読み込みます。|  
|[CPaneFrameWnd::OnBeforeDock](../Topic/CPaneFrameWnd::OnBeforeDock.md)|ドッキングが可能かどうかを判定します。|  
|[CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md)|ミニフレーム ウィンドウを直前の位置にドッキングします。|  
|[CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md)|ロールアップ タイマーを停止します。|  
|[CPaneFrameWnd::OnMovePane](../Topic/CPaneFrameWnd::OnMovePane.md)|ミニフレーム ウィンドウを指定したオフセットだけ移動します。|  
|[CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md)|含まれているペインのレイアウトを調整します。|  
|[CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md)|ロールアップ タイマーを設定します。|  
|[CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md)|ミニフレーム ウィンドウ内のペインが非表示になるとき、または表示されるときに、フレームワークによって呼び出されます。|  
|[CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md)|ユーザーが指定した位置がミニフレーム ウィンドウ内のペインに含まれている場合、そのペインを返します。|  
|[CPaneFrameWnd::Pin](../Topic/CPaneFrameWnd::Pin.md)||  
|`CPaneFrameWnd::PreTranslateMessage`|[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) と [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) の各 Windows 関数にディスパッチされる前に、ウィンドウ メッセージを変換するためにクラス [CWinApp](../../mfc/reference/cwinapp-class.md) で使用されます。|  
|[CPaneFrameWnd::RedrawAll](../Topic/CPaneFrameWnd::RedrawAll.md)|すべてのミニフレーム ウィンドウを再描画します。|  
|[CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md)|有効でないウィンドウを削除するために、フレームワークによって呼び出されます。|  
|[CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md)|ミニフレーム ウィンドウから、ペインを削除します。|  
|[CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md)|ペインを別のペインに置き換えます。|  
|[CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md)|レジストリにペインの状態を保存します。|  
|`CPaneFrameWnd::Serialize`|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。|  
|[CPaneFrameWnd::SetCaptionButtons](../Topic/CPaneFrameWnd::SetCaptionButtons.md)|キャプションのボタンを設定します。|  
|[CPaneFrameWnd::SetDelayShow](../Topic/CPaneFrameWnd::SetDelayShow.md)||  
|[CPaneFrameWnd::SetDockingManager](../Topic/CPaneFrameWnd::SetDockingManager.md)||  
|[CPaneFrameWnd::SetDockingTimer](../Topic/CPaneFrameWnd::SetDockingTimer.md)|ドッキング タイマーを設定します。|  
|[CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md)|ドッキング状態を設定します。|  
|[CPaneFrameWnd::SetHotPoint](../Topic/CPaneFrameWnd::SetHotPoint.md)||  
|[CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md)|ドッキング前の状態を設定するために、フレームワークによって呼び出されます。|  
|[CPaneFrameWnd::SizeToContent](../Topic/CPaneFrameWnd::SizeToContent.md)|含まれているペインとサイズを同じにするために、ミニフレーム ウィンドウのサイズを調整します。|  
|[CPaneFrameWnd::StartTearOff](../Topic/CPaneFrameWnd::StartTearOff.md)|メニューをティアオフします。|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md)||  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPaneFrameWnd::OnCheckRollState](../Topic/CPaneFrameWnd::OnCheckRollState.md)|ミニフレーム ウィンドウをロール アップまたはロール ダウンするかどうかを判断します。|  
|[CPaneFrameWnd::OnDrawBorder](../Topic/CPaneFrameWnd::OnDrawBorder.md)|ミニフレーム ウィンドウの境界線を描画します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPaneFrameWnd::m\_bUseSaveBits](../Topic/CPaneFrameWnd::m_bUseSaveBits.md)|`CS_SAVEBITS` クラス スタイルにウィンドウ クラスを登録するかどうかを指定します。|  
  
## 解説  
 ペインがドッキング状態からフローティング状態に切り替わるときに、フレームワークは自動的に `CPaneFrameWnd` オブジェクトを作成します。  
  
 ミニフレーム ウィンドウは内容を表示した状態でドラッグ \(直接ドッキング\) するか、ドラッグ四角形を使用してドラッグ \(標準ドッキング\) することができます。  ミニフレームのコンテナー ペインのドッキング モードにより、ミニフレームのドラッグ動作が決まります。  詳細については、「[CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md)」を参照してください。  
  
 ミニフレーム ウィンドウには、含まれているペインのスタイルに従って、キャプションのボタンが表示されます。  ペインを閉じることができる場合は \([CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)\)、\[閉じる\] ボタンが表示されます。  ペインのスタイルが `AFX_CBRS_AUTO_ROLLUP` である場合は、ピンが表示されます。  
  
 `CPaneFrameWnd` からクラスを派生させる場合は、フレームワークで作成方法を定義する必要があります。  [CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md) をオーバーライドしてクラスを作成するか、クラスのランタイム クラス情報を示すよう `CPane::m_pMiniFrameRTC` メンバーを設定します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
## 必要条件  
 **ヘッダー:** afxPaneFrameWnd.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)