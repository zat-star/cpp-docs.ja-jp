---
title: "CDockablePaneAdapter クラス | Microsoft Docs"
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
  - "CDockablePaneAdapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockablePaneAdapter クラス"
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDockablePaneAdapter クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CWnd` の派生ペインのドッキングをサポートします。  
  
## 構文  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDockablePaneAdapter::GetWrappedWnd](../Topic/CDockablePaneAdapter::GetWrappedWnd.md)|ラップされたウィンドウを返します。|  
|[CDockablePaneAdapter::LoadState](../Topic/CDockablePaneAdapter::LoadState.md)|\([CDockablePane::LoadState](http://msdn.microsoft.com/ja-jp/96110136-4f46-4764-8a76-3b4abaf77917) をオーバーライドします。\)|  
|[CDockablePaneAdapter::SaveState](../Topic/CDockablePaneAdapter::SaveState.md)|\([CDockablePane::SaveState](http://msdn.microsoft.com/ja-jp/c5c24249-8d0d-46cb-96d9-9f5c6dc191db) をオーバーライドします。\)|  
|[CDockablePaneAdapter::SetWrappedWnd](../Topic/CDockablePaneAdapter::SetWrappedWnd.md)||  
  
## 解説  
 通常、[CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) メソッドまたは [CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md) メソッドを使用する場合に、フレームワークはこのクラスのオブジェクトをインスタンス化します。  
  
 `CDockablePaneAdapter` の動作をカスタマイズする場合は、単にそこから新しいクラスを派生させ、[CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md) を使用してタブ付きウィンドウにランタイム クラス情報を設定します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md) [CCmdTarget](../Topic/CCmdTarget%20Class.md) [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../Topic/CDockablePane%20Class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## 必要条件  
 **ヘッダー:** afxDockablePaneAdapter.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CDockablePane クラス](../Topic/CDockablePane%20Class.md)