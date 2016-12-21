---
title: "CPaneDivider クラス | Microsoft Docs"
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
  - "CPaneDivider"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneDivider クラス"
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneDivider クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 `CPaneDivider` クラスは、メイン フレーム ウィンドウのクライアント領域から、2 つのペインを分割、ペインの 2 つのグループを分割、または 1 つのグループのペインを分離します。  
  
## 構文  
  
```  
class CPaneDivider : public CBasePane  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPaneDivider::CPaneDivider](../Topic/CPaneDivider::CPaneDivider.md)||  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPaneDivider::AddPaneContainer](../Topic/CPaneDivider::AddPaneContainer.md)||  
|[CPaneDivider::AddPane](../Topic/CPaneDivider::AddPane.md)||  
|[CPaneDivider::AddRecentPane](../Topic/CPaneDivider::AddRecentPane.md)||  
|[CPaneDivider::CalcExpectedDockedRect](../Topic/CPaneDivider::CalcExpectedDockedRect.md)||  
|[CPaneDivider::CalcFixedLayout](../Topic/CPaneDivider::CalcFixedLayout.md)|\([CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md) をオーバーライドします。\)|  
|[CPaneDivider::CheckVisibility](../Topic/CPaneDivider::CheckVisibility.md)||  
|[CPaneDivider::CreateEx](../Topic/CPaneDivider::CreateEx.md)|\([CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md) をオーバーライドします。\)|  
|[CPaneDivider::DoesAllowDynInsertBefore](../Topic/CPaneDivider::DoesAllowDynInsertBefore.md)|\([CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md) をオーバーライドします。\)|  
|[CPaneDivider::DoesContainFloatingPane](../Topic/CPaneDivider::DoesContainFloatingPane.md)||  
|[CPaneDivider::FindPaneContainer](../Topic/CPaneDivider::FindPaneContainer.md)||  
|[CPaneDivider::FindTabbedPane](../Topic/CPaneDivider::FindTabbedPane.md)||  
|[CPaneDivider::GetDefaultWidth](../Topic/CPaneDivider::GetDefaultWidth.md)||  
|[CPaneDivider::GetFirstPane](../Topic/CPaneDivider::GetFirstPane.md)||  
|[CPaneDivider::GetPaneDividerStyle](../Topic/CPaneDivider::GetPaneDividerStyle.md)||  
|[CPaneDivider::GetRootContainerRect](../Topic/CPaneDivider::GetRootContainerRect.md)||  
|[CPaneDivider::GetWidth](../Topic/CPaneDivider::GetWidth.md)||  
|[CPaneDivider::Init](../Topic/CPaneDivider::Init.md)||  
|[CPaneDivider::InsertPane](../Topic/CPaneDivider::InsertPane.md)||  
|[CPaneDivider::IsAutoHideMode](../Topic/CPaneDivider::IsAutoHideMode.md)|\([CBasePane::IsAutoHideMode](../Topic/CBasePane::IsAutoHideMode.md) をオーバーライドします。\)|  
|[CPaneDivider::IsDefault](../Topic/CPaneDivider::IsDefault.md)||  
|[CPaneDivider::IsHorizontal](../Topic/CPaneDivider::IsHorizontal.md)|\([CBasePane::IsHorizontal](../Topic/CBasePane::IsHorizontal.md) をオーバーライドします。\)|  
|[CPaneDivider::Move](../Topic/CPaneDivider::Move.md)||  
|[CPaneDivider::NotifyAboutRelease](../Topic/CPaneDivider::NotifyAboutRelease.md)||  
|[CPaneDivider::OnShowPane](../Topic/CPaneDivider::OnShowPane.md)||  
|[CPaneDivider::ReleaseEmptyPaneContainers](../Topic/CPaneDivider::ReleaseEmptyPaneContainers.md)||  
|[CPaneDivider::RemovePane](../Topic/CPaneDivider::RemovePane.md)||  
|[CPaneDivider::ReplacePane](../Topic/CPaneDivider::ReplacePane.md)||  
|[CPaneDivider::RepositionPanes](../Topic/CPaneDivider::RepositionPanes.md)||  
|[CPaneDivider::Serialize](../Topic/CPaneDivider::Serialize.md)|\(`CBasePane::Serialize` をオーバーライドします。\)|  
|[CPaneDivider::SetAutoHideMode](../Topic/CPaneDivider::SetAutoHideMode.md)||  
|[CPaneDivider::SetPaneContainerManager](../Topic/CPaneDivider::SetPaneContainerManager.md)||  
|[CPaneDivider::ShowWindow](../Topic/CPaneDivider::ShowWindow.md)||  
|[CPaneDivider::StoreRecentDockSiteInfo](../Topic/CPaneDivider::StoreRecentDockSiteInfo.md)||  
|[CPaneDivider::StoreRecentTabRelatedInfo](../Topic/CPaneDivider::StoreRecentTabRelatedInfo.md)||  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPaneDivider::GetPanes](../Topic/CPaneDivider::GetPanes.md)|[CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md) に存在するペインのリストを返します。  このメソッドは、既定のペイン区分線に対してのみ呼び出すようにしてください。|  
|[CPaneDivider::GetPaneDividers](../Topic/CPaneDivider::GetPaneDividers.md)|[CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md) に存在するペイン区分線のリストを返します。  このメソッドは、既定のペイン区分線に対してのみ呼び出すようにしてください。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPaneDivider::m\_nDefaultWidth](../Topic/CPaneDivider::m_nDefaultWidth.md)|アプリケーション内のすべてのペイン区分線の既定の幅をピクセル単位で指定します。|  
|[CPaneDivider::m\_pSliderRTC](../Topic/CPaneDivider::m_pSliderRTC.md)|`CPaneDivider` の派生オブジェクトのランタイム クラス情報へのポインターを保持します。|  
  
## 解説  
 ペインがドッキングされると、フレームワークにより自動的に `CPaneDivider` オブジェクトが作成されます。  
  
 ペイン区分線には次の 2 種類があります。  
  
-   既定のペイン区分線は、ペインのグループがメイン フレーム ウィンドウの横にドッキングされたときに作成されます。  既定のペイン区分線は、[CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)へのポインターを保持し、ペインのサイズ変更、別のペインやコンテナーへのドッキングなど、ペインのグループに対する多くの操作をコンテナー マネージャーにリダイレクトします。  各ドッキング ペインには、既定のペイン区分線へのポインターが維持されます。  
  
-   標準のペイン区分線は、コンテナー内の 2 つのペインを分割するだけです。  詳細については、「[CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)」を参照してください。  
  
## 使用例  
 `CWorkspaceBar` オブジェクトから `CPaneDivider` オブジェクトを取得する方法を次の例に示します。  このコード スニペットは [MDI サンプルは、デモを記録します。](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/CPP/cpanedivider-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md) [CCmdTarget](../Topic/CCmdTarget%20Class.md) [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPaneDivider](../../mfc/reference/cpanedivider-class.md)  
  
## 必要条件  
 **ヘッダー :** afxPaneDivider.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)   
 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)   
 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)   
 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)