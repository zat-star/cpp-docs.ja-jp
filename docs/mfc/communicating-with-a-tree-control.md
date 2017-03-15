---
title: "ツリー コントロールとの情報のやり取り | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "通信, ツリー コントロール"
  - "CTreeCtrl クラス, 呼び出し (メンバー関数を)"
  - "ツリー コントロール"
  - "ツリー コントロール, 通信"
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ツリー コントロールとの情報のやり取り
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクトがどのようにして作成したか [CTreeCtrl](../mfc/reference/ctreectrl-class.md) オブジェクトのメンバー関数を呼び出すと、さまざまな方法を使用して T:  
  
-   ツリー コントロールがダイアログ ボックス内にある場合は、ダイアログ ボックス クラスで作成する `CTreeCtrl` 型のメンバー変数を使用します。  
  
-   ツリー コントロールが子ウィンドウ、`CTreeCtrl` オブジェクトを使用して、ポインターを\) オブジェクトを構築するために使用します。  
  
-   `CTreeView` オブジェクトを使用する場合は、ツリー コントロールへの参照を取得するに [CTreeView::GetTreeCtrl](../Topic/CTreeView::GetTreeCtrl.md) 関数を使用します。  この値の別の参照を初期化するか、`CTreeCtrl` のポインターへの参照のアドレスを割り当てることができます。  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)