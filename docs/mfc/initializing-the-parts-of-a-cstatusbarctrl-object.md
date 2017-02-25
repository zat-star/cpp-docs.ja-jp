---
title: "CStatusBarCtrl オブジェクトの区画の初期化 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl クラス, 宣言 (部分)"
  - "CStatusBarCtrl クラス, 簡易モード"
  - "アイコン, 使用 (ステータス バーで)"
  - "簡易ステータス バー"
  - "ステータス バー, 宣言 (部分)"
  - "ステータス バー, アイコン"
  - "ステータス バー, 簡易モード"
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CStatusBarCtrl オブジェクトの区画の初期化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既定で、別のペインを使用して、ステータス バー ステータス情報が表示されます。  これらのペインは \(または部分とも呼ばれます\) 文字列、アイコン、またはその両方を含めることができます。  
  
 複数のパーツがと長さが、ステータス バーである方法を定義するために [SetParts](../Topic/CStatusBarCtrl::SetParts.md) を使用します。  ステータス バーの一部を作成したら、ステータス バーの特定の部分のテキストまたはアイコンを設定するに [SetText](../Topic/CStatusBarCtrl::SetText.md) と [SetIcon](../Topic/CStatusBarCtrl::SetIcon.md) に呼び出しを行ってください。  一度パートは、通常、コントロールに自動的に再描画されます設定されました。  
  
 次の例は、4 種類のペインを持つ `CStatusBarCtrl` の既存のオブジェクト \(`m_StatusBarCtrl`\) を初期化し、アイコン \(IDI\_ICON1\) と 2 番目のテキストを設定します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/CPP/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]  
  
 簡単に `CStatusBarCtrl` オブジェクト モードの設定の詳細については、「[CStatusBarCtrl オブジェクト モードの設定](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)」を参照してください。  
  
## 参照  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)