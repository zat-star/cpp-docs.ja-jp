---
title: "CToolTipCtrl を使用して CToolTipCtrl オブジェクトを作成および操作する方法 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl クラス, 使用"
  - "ツール ヒント [C++], 作成"
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CToolTipCtrl を使用して CToolTipCtrl オブジェクトを作成および操作する方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md) の使用例を次に示します。:  
  
### CToolTipCtrl を作成および処理します。  
  
1.  `CToolTipCtrl` オブジェクトを構築します。  
  
2.  Windows のツール ヒントのコモン コントロールを作成し、`CToolTipCtrl` オブジェクトに接続するに [作成](../Topic/CToolTipCtrl::Create.md) を呼び出します。  
  
3.  カーソルがツールには、ツール ヒントに格納されている情報が表示されるように、ツール ヒント コントロールを持つツールを登録するに [AddTool](../Topic/CToolTipCtrl::AddTool.md) を呼び出します。  
  
4.  ツール ヒントをツールを管理する情報を設定するには、[SetToolInfo](../Topic/CToolTipCtrl::SetToolInfo.md) を呼び出します。  
  
5.  ツールの外接する新しい四角形を設定するために [SetToolRect](../Topic/CToolTipCtrl::SetToolRect.md) を呼び出します。  
  
6.  ポイントを特定のツールの外接する四角形内にある呼び出し、そのとツールに関する情報を取得して、かどうかをテストするために [HitTest](../Topic/CToolTipCtrl::HitTest.md) を。  
  
7.  ツール ヒント コントロールに登録されているツールの数を取得するために [GetToolCount](../Topic/CToolTipCtrl::GetToolCount.md) を呼び出します。  
  
## 参照  
 [CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)   
 [コントロール](../mfc/controls-mfc.md)