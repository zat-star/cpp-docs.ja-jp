---
title: "コンパイラの警告 (レベル 2 および 3) C4008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4008"
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 2 および 3) C4008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 'attribute' 属性は無視されました  
  
 コンパイラは、関数 \(レベル 3 警告\) またはデータ \(レベル 2 警告\) の `__fastcall`、**静的**、または**インライン**属性を無視しました。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  データを伴う `__fastcall` 属性。  
  
2.  **メイン**関数の**静的**または**インライン**属性。