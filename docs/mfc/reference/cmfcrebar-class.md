---
title: "CMFCReBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCReBar クラス"
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCReBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCReBar` オブジェクトは、Rebar コントロールのレイアウト、永続性、および状態の情報を提供するコントロール バーです。  
  
## 構文  
  
```  
class CMFCReBar : public CPane  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCReBar::AddBar](../Topic/CMFCReBar::AddBar.md)|Rebar にバンドを追加します。|  
|[CMFCReBar::CalcFixedLayout](../Topic/CMFCReBar::CalcFixedLayout.md)|\([CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md) をオーバーライドします。\)|  
|[CMFCReBar::CanFloat](../Topic/CMFCReBar::CanFloat.md)|\([CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md) をオーバーライドします。\)|  
|[CMFCReBar::Create](../Topic/CMFCReBar::Create.md)|Rebar コントロールを作成し、`CMFCReBar` オブジェクトに結び付けます。|  
|[CMFCReBar::EnableDocking](../Topic/CMFCReBar::EnableDocking.md)|\([CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) をオーバーライドします。\)|  
|[CMFCReBar::GetReBarBandInfoSize](../Topic/CMFCReBar::GetReBarBandInfoSize.md)||  
|[CMFCReBar::GetReBarCtrl](../Topic/CMFCReBar::GetReBarCtrl.md)|基になるコモン コントロールである [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) に直接アクセスできるようにします。|  
|[CMFCReBar::OnShowControlBarMenu](../Topic/CMFCReBar::OnShowControlBarMenu.md)|\([CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md) をオーバーライドします\)。|  
|[CMFCReBar::OnToolHitTest](../Topic/CMFCReBar::OnToolHitTest.md)|\([CWnd::OnToolHitTest](../Topic/CWnd::OnToolHitTest.md) をオーバーライドします。\)|  
|[CMFCReBar::OnUpdateCmdUI](../Topic/CMFCReBar::OnUpdateCmdUI.md)|\([CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/ja-jp/e139f06a-9793-4ee2-bc3d-517389368c77) をオーバーライドします。\)|  
|[CMFCReBar::SetPaneAlignment](../Topic/CMFCReBar::SetPaneAlignment.md)|\([CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md) をオーバーライドします。\)|  
  
## 解説  
 `CMFCReBar` オブジェクトには、さまざまな子ウィンドウを格納できます。  たとえば、エディット ボックス、ツール バー、リスト ボックスなどです。  Rebar のサイズはプログラムで変更できます。ユーザーは、グリップ バーをドラッグして、Rebar のサイズを手動で変更できます。  Rebar オブジェクトの背景を選択したビットマップに設定することもできます。  
  
 Rebar オブジェクトは、ツール バー オブジェクトに似ています。  Rebar コントロールには、バンドをいくつでも格納できます。バンドごとに、グリップ バー、ビットマップ、テキスト ラベル、子ウィンドウを格納できます。  
  
## 使用例  
 次の例は、`CMFCReBar` クラスのさまざまなメソッドの使用方法を説明しています。  Rebar コントロールを作成し、そのコントロールにバンドを追加する方法を示しています。  バンドは内部ツール バーとして機能します。  このコード スニペットは [rebar のテストの例](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/CPP/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/CPP/cmfcrebar-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md) [CCmdTarget](../Topic/CCmdTarget%20Class.md) [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxRebar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CReBarCtrl クラス](../../mfc/reference/crebarctrl-class.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)