---
title: "オーバーライド可能な CWinApp のメンバー関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application クラス"
  - "CWinApp クラス, オーバーライド可能な"
  - "オーバーライド, オーバーライド可能な関数 (CWinApp の)"
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# オーバーライド可能な CWinApp のメンバー関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinApp](../mfc/reference/cwinapp-class.md) は 複数のキー オーバーライドできるなメンバー関数が用意されています \(`CWinApp` は `CWinApp` が派生する\) クラス [CWinThread](../mfc/reference/cwinthread-class.md)からこれらのメンバーをオーバーライドして、:  
  
-   [InitInstance](../mfc/initinstance-member-function.md)  
  
-   [&#91;実行&#93;](../Topic/Run%20Member%20Function.md)  
  
-   [ExitInstance](../mfc/exitinstance-member-function.md)  
  
-   [OnIdle](../mfc/onidle-member-function.md)  
  
 継承した設定をオーバーライドする必要 `CWinApp` のメンバー関数は `InitInstance`です。  
  
## 参照  
 [CWinApp : アプリケーション クラス](../Topic/CWinApp:%20The%20Application%20Class.md)