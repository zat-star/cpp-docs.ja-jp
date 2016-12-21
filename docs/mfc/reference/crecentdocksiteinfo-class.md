---
title: "CRecentDockSiteInfo クラス | Microsoft Docs"
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
  - "CRecentDockSiteInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecentDockSiteInfo クラス"
ms.assetid: 2dd14f95-d5a2-4461-a7a5-2c6c36a3a165
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRecentDockSiteInfo クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CRecentDockSiteInfo` クラスは、[CPane クラス](../../mfc/reference/cpane-class.md)の最近の状態情報を格納するヘルパー クラスです。  
  
## 構文  
  
```  
class CRecentDockSiteInfo : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CRecentDockSiteInfo::CRecentDockSiteInfo`|既定のコンストラクター|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRecentDockSiteInfo::CleanUp](../Topic/CRecentDockSiteInfo::CleanUp.md)||  
|[CRecentDockSiteInfo::GetRecentDefaultPaneDivider](../Topic/CRecentDockSiteInfo::GetRecentDefaultPaneDivider.md)||  
|[CRecentDockSiteInfo::GetRecentDockedPercent](../Topic/CRecentDockSiteInfo::GetRecentDockedPercent.md)||  
|[CRecentDockSiteInfo::GetRecentDockedRect](../Topic/CRecentDockSiteInfo::GetRecentDockedRect.md)||  
|[CRecentDockSiteInfo::GetRecentListOfPanes](../Topic/CRecentDockSiteInfo::GetRecentListOfPanes.md)||  
|[CRecentDockSiteInfo::GetRecentPaneContainer](../Topic/CRecentDockSiteInfo::GetRecentPaneContainer.md)||  
|[CRecentDockSiteInfo::GetRecentTabContainer](../Topic/CRecentDockSiteInfo::GetRecentTabContainer.md)||  
|[CRecentDockSiteInfo::Init](../Topic/CRecentDockSiteInfo::Init.md)||  
|[CRecentDockSiteInfo::IsRecentLeftPane](../Topic/CRecentDockSiteInfo::IsRecentLeftPane.md)||  
|[CRecentDockSiteInfo::operator \=](../Topic/CRecentDockSiteInfo::operator%20=.md)||  
|[CRecentDockSiteInfo::SaveListOfRecentPanes](../Topic/CRecentDockSiteInfo::SaveListOfRecentPanes.md)||  
|[CRecentDockSiteInfo::SetInfo](../Topic/CRecentDockSiteInfo::SetInfo.md)||  
|[CRecentDockSiteInfo::StoreDockInfo](../Topic/CRecentDockSiteInfo::StoreDockInfo.md)||  
  
## 解説  
 `CRecentDockSiteInfo` クラスは、データ管理クラスです。  ドッキング状態とフローティング状態の間で切り替わる `CPane` の最後の状態を追跡します。  ユーザーがフローティング状態のドッキング可能ペインをダブルクリックすると、ペインはドッキング状態になります。  ドッキング状態のペインをダブルクリックすると、ペインは前の位置、サイズ、および状態に戻ります。  同様に、ペインを再びドッキング状態にすると、前のドッキング位置が復元されます。  このデータ クラスは、この機能を実現します。  このクラスのメンバーはドッキング状態のペインの状態情報を格納するため、アプリケーションで直接変更しないでください。  
  
 `CRecentDockSiteInfo` オブジェクトは、ペインが作成されるたびに作成されます。  それぞれの `CPane` オブジェクトは、この情報を格納するためのメンバー変数 [CPane::m\_recentDockInfo](../Topic/CPane::m_recentDockInfo.md) を持ちます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrecentDockSiteInfo.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CDockSite クラス](../../mfc/reference/cdocksite-class.md)