---
title: "CPane クラス | Microsoft Docs"
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
  - "CPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPane クラス"
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPane クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CPane` クラスは、[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)の拡張版です。  既存の MFC プロジェクトをアップグレードした場合、`CPane`と `CControlBar` のすべてに置き換えます。  
  
## 構文  
  
```  
class CPane : public CBasePane  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CPane::~CPane`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md)|ペインのレイアウトをすぐに再計算します。|  
|[CPane::AllocElements](../Topic/CPane::AllocElements.md)|内部使用のためにストレージを割り当てます。|  
|[CPane::AllowShowOnPaneMenu](../Topic/CPane::AllowShowOnPaneMenu.md)|ウィンドウがアプリケーションのウィンドウのランタイム生成されたリストに一覧表示されているかどうかを指定します。|  
|[CPane::CalcAvailableSize](../Topic/CPane::CalcAvailableSize.md)|指定された四角形と現在のウィンドウ四角形のサイズの差を計算します。|  
|[CPane::CalcInsideRect](../Topic/CPane::CalcInsideRect.md)|ペインの内側の四角形を計算します \(境界線とグリッパーを含む\)。|  
|[CPane::CalcRecentDockedRect](../Topic/CPane::CalcRecentDockedRect.md)|最近ドッキングされた四角形を計算します。|  
|[CPane::CalcSize](../Topic/CPane::CalcSize.md)|ペインのサイズを計算します。|  
|[CPane::CanBeDocked](../Topic/CPane::CanBeDocked.md)|ペインを指定した基本ペインにドッキングできるかどうかを判定します。|  
|[CPane::CanBeTabbedDocument](../Topic/CPane::CanBeTabbedDocument.md)|ペインをタブ付きドキュメントに変換できるかどうかを判定します。|  
|[CPane::ConvertToTabbedDocument](../Topic/CPane::ConvertToTabbedDocument.md)|タブ付きドキュメントにドッキングできるペインを変換します。|  
|[CPane::CopyState](../Topic/CPane::CopyState.md)|ペインの状態をコピーします   \([CBasePane::CopyState](../Topic/CBasePane::CopyState.md) をオーバーライドします\)。|  
|[CPane::Create](../Topic/CPane::Create.md)|コントロール バーを作成し、それを `CPane` オブジェクトにアタッチします。|  
|[CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md)|浮動ペインのミニフレーム ウィンドウを作成します。|  
|[CPane::CreateEx](../Topic/CPane::CreateEx.md)|コントロール バーを作成し、それを `CPane` オブジェクトにアタッチします。|  
|`CPane::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|[CPane::DockByMouse](../Topic/CPane::DockByMouse.md)|マウスのドッキング方法を使用して、ペインをドッキングします。|  
|[CPane::DockPane](../Topic/CPane::DockPane.md)|浮動ペインを基本ペインにドッキングします。|  
|[CPane::DockPaneStandard](../Topic/CPane::DockPaneStandard.md)|アウトラインの \(標準\) を使用してドッキング ペインをドッキングします。|  
|[CPane::DockToFrameWindow](../Topic/CPane::DockToFrameWindow.md)|ドッキング可能ペインをフレームにドッキングします。  \(`CBasePane::DockToFrameWindow` をオーバーライドします。\)|  
|[CPane::DoesAllowSiblingBars](../Topic/CPane::DoesAllowSiblingBars.md)|現在のペインをドッキングしている行の別のペインをドッキングできるかどうかを示します。|  
|[CPane::FloatPane](../Topic/CPane::FloatPane.md)|ペインをフローティング状態にします。|  
|[CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md)|量を配置できるペインをピクセル単位で返します。|  
|[CPane::GetAvailableStretchSize](../Topic/CPane::GetAvailableStretchSize.md)|量を、ウィンドウが縮小できるピクセル単位で返します。|  
|[CPane::GetBorders](../Topic/CPane::GetBorders.md)|ペインの境界線の幅を返します。|  
|[CPane::GetClientHotSpot](../Topic/CPane::GetClientHotSpot.md)|ウィンドウの *ホット スポットを* 返します。|  
|[CPane::GetDockSiteRow](../Topic/CPane::GetDockSiteRow.md)|ペインがドッキングされているドッキング行を返します。|  
|[CPane::GetExclusiveRowMode](../Topic/CPane::GetExclusiveRowMode.md)|ペインが排他的行モードかどうかを判定します。|  
|[CPane::GetHotSpot](../Topic/CPane::GetHotSpot.md)|`CMFCDragFrameImpl` の基になるオブジェクトに格納されているホット スポットを返します。|  
|[CPane::GetMinSize](../Topic/CPane::GetMinSize.md)|ウィンドウのサイズを指定された最小値を取得します。|  
|[CPane::GetPaneName](../Topic/CPane::GetPaneName.md)|ウィンドウのタイトルを取得します。|  
|`CPane::GetResizeStep`|内部使用。|  
|`CPane::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CPane::GetVirtualRect](../Topic/CPane::GetVirtualRect.md)|ウィンドウの仮想 *四角形を* 取得します。|  
|[CPane::IsChangeState](../Topic/CPane::IsChangeState.md)|ウィンドウが実行されると、このメソッドは、他のウィンドウに対してウィンドウの位置を解析し、行およびミニフレーム ウィンドウを返します `AFX_CS_STATUS` の適切な値ドッキングします。|  
|[CPane::IsDragMode](../Topic/CPane::IsDragMode.md)|ウィンドウをドラッグするかどうかを指定します。|  
|[CPane::IsInFloatingMultiPaneFrameWnd](../Topic/CPane::IsInFloatingMultiPaneFrameWnd.md)|ウィンドウが複数のウィンドウ フレーム ウィンドウにあるかどうかを指定します。  \(`CBasePane::IsInFloatingMultiPaneFrameWnd` をオーバーライドします。\)|  
|[CPane::IsLeftOf](../Topic/CPane::IsLeftOf.md)|ウィンドウ \(またはそれ以上\) に指定された四角形になっているかどうかを判定します。|  
|[CPane::IsResizable](../Topic/CPane::IsResizable.md)|ペインのサイズを変更できるかどうかを判定します。  \([CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md) をオーバーライドします\)。|  
|[CPane::IsTabbed](../Topic/CPane::IsTabbed.md)|ペインがタブ付きウィンドウのタブ コントロールに挿入されているかどうかを調べます。  \([CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md) をオーバーライドします\)。|  
|[CPane::LoadState](../Topic/CPane::LoadState.md)|レジストリからの状態を読み込みます。  \([CBasePane::LoadState](../Topic/CBasePane::LoadState.md) をオーバーライドします\)。|  
|[CPane::MoveByAlignment](../Topic/CPane::MoveByAlignment.md)|指定されたウィンドウ、および仮想四角形を移動します。|  
|[CPane::MovePane](../Topic/CPane::MovePane.md)|指定された四角形にペインを移動します。|  
|[CPane::OnAfterChangeParent](../Topic/CPane::OnAfterChangeParent.md)|ペインの親が変更されたときに、フレームワークによって呼び出されます。|  
|[CPane::OnBeforeChangeParent](../Topic/CPane::OnBeforeChangeParent.md)|ペインの親が変更される直前に、フレームワークによって呼び出されます。|  
|[CPane::OnPressCloseButton](../Topic/CPane::OnPressCloseButton.md)|ユーザーがペインのキャプションに閉じるボタンを選択したときに、フレームワークによって呼び出されます。|  
|`CPane::OnProcessDblClk`|内部使用。|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|特殊なペイン メニューが表示される直前に、フレームワークによって呼び出されます。|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|特殊なペイン メニューが表示される直前に、フレームワークによって呼び出されます。|  
|`CPane::PrepareToDock`|内部使用。|  
|[CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md)|ウィンドウのレイアウト情報を再計算します。  \([CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md) をオーバーライドします。\)|  
|[CPane::SaveState](../Topic/CPane::SaveState.md)|ウィンドウの状態をレジストリに保存します。  \([CBasePane::SaveState](../Topic/CBasePane::SaveState.md) をオーバーライドします\)。|  
|[CPane::SetActiveInGroup](../Topic/CPane::SetActiveInGroup.md)|アクティブとしてウィンドウにフラグを設定します。|  
|[CPane::SetBorders](../Topic/CPane::SetBorders.md)|ペインの境界線のサイズ値を設定します。|  
|[CPane::SetClientHotSpot](../Topic/CPane::SetClientHotSpot.md)|ウィンドウのホット スポットを設定します。|  
|[CPane::SetDockState](../Topic/CPane::SetDockState.md)|ウィンドウの状態情報をドッキングする場合。|  
|[CPane::SetExclusiveRowMode](../Topic/CPane::SetExclusiveRowMode.md)|排他的行モードを有効または無効にします。|  
|[CPane::SetMiniFrameRTC](../Topic/CPane::SetMiniFrameRTC.md)|既定のミニフレーム ウィンドウのランタイム クラス情報を設定します。|  
|[CPane::SetMinSize](../Topic/CPane::SetMinSize.md)|最小をウィンドウのサイズを指定します。|  
|[CPane::SetVirtualRect](../Topic/CPane::SetVirtualRect.md)|ウィンドウの仮想 *四角形を* 設定します。|  
|[CPane::StretchPaneDeferWndPos](../Topic/CPane::StretchPaneDeferWndPos.md)|ウィンドウをドッキング スタイルまたは方向に基づいて垂直方向に伸縮します。|  
|[CPane::ToggleAutoHide](../Topic/CPane::ToggleAutoHide.md)|自動非表示モードに切り替えます。|  
|[CPane::UndockPane](../Topic/CPane::UndockPane.md)|ペインが現在ドッキングしているドッキング サイト、既定スライダー、またはミニフレーム ウィンドウからそのペインを削除します   \([CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md) をオーバーライドします\)。|  
|[CPane::UpdateVirtualRect](../Topic/CPane::UpdateVirtualRect.md)|仮想四角形を更新します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPane::OnAfterDock](../Topic/CPane::OnAfterDock.md)|ペインがドッキングしたときに、フレームワークによって呼び出されます。|  
|[CPane::OnAfterFloat](../Topic/CPane::OnAfterFloat.md)|ペインがフローティング状態になったときに、フレームワークによって呼び出されます。|  
|[CPane::OnBeforeDock](../Topic/CPane::OnBeforeDock.md)|ペインのドッキングを開始するときに、フレームワークによって呼び出されます。|  
|[CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md)|ペインがフローティング状態になる直前に、フレームワークによって呼び出されます。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPane::m\_bHandleMinSize](../Topic/CPane::m_bHandleMinSize.md)|ペインの最小サイズの一貫した処理を有効にします。|  
|[CPane::m\_recentDockInfo](../Topic/CPane::m_recentDockInfo.md)|最新のドッキング情報を提供します。|  
  
## 解説  
 通常、`CPane` のオブジェクトを直接インスタンス化されません。  ドッキング機能を持つペインが必要な場合は、[CDockablePane](../Topic/CDockablePane%20Class.md)からのオブジェクトを取得します。  ツール バー機能が必要な場合は、[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)からのオブジェクトを取得します。  
  
 `CPane`からクラスを派生させる場合に、[CDockSite](../../mfc/reference/cdocksite-class.md) にドッキングし、[CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)でフローティングできます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## 必要条件  
 **ヘッダー :** afxPane.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)