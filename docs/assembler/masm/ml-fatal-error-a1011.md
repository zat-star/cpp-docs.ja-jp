---
title: "ML Fatal Error A1011 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1011"
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**ディレクティブはコントロール ブロックでなければなりません**  
  
 アセンブラーは 1 が予期されていない高度なディレクティブが見つかりました。  次のディレクティブの 1 つが検索 :  
  
-   [.IF](../Topic/.IF.md) のない [.ELSE](../../assembler/masm/dot-else.md)  
  
-   [.IF](../Topic/.IF.md) のない [.ENDIF](../../assembler/masm/dot-endif.md)  
  
-   [.WHILE](../../assembler/masm/dot-while.md) のない [.ENDW](../../assembler/masm/dot-endw.md)  
  
-   [.REPEAT](../../assembler/masm/dot-repeat.md) のない [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md)  
  
-   [.WHILE](../../assembler/masm/dot-while.md) または [.REPEAT](../../assembler/masm/dot-repeat.md) のない [.CONTINUE](../Topic/.CONTINUE.md)  
  
-   [.WHILE](../../assembler/masm/dot-while.md) または [.REPEAT](../../assembler/masm/dot-repeat.md) のない [.BREAK](../../assembler/masm/dot-break.md)  
  
-   `.ELSE` の [.ELSE](../../assembler/masm/dot-else.md)  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)