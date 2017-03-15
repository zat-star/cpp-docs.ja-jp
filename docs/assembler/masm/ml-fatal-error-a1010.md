---
title: "ML Fatal Error A1010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1010"
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**" ブロックの入れ子 :**  
  
 ブロックの先頭と一致します。正規表現が存在しないことまたはブロックの最後に一致した先頭がありません。  次のいずれかに含まれる可能性があります :  
  
-   [.IF](../Topic/.IF.md) [.REPEAT](../../assembler/masm/dot-repeat.md)または [.WHILE](../../assembler/masm/dot-while.md) 高レベルのディレクティブ。  
  
-   [IF](../../assembler/masm/if-masm.md) [繰り返し](../../assembler/masm/repeat.md)または  **と**  などの条件付きアセンブリのディレクティブ。  
  
-   構造体または共用体の定義。  
  
-   プロシージャ定義。  
  
-   部分定義。  
  
-   [POPCONTEXT](../../assembler/masm/popcontext.md) のディレクティブ。  
  
-   一致する [IF](../../assembler/masm/if-masm.md) のない [else](../Topic/ELSE%20\(MASM\).md)[ELSEIF](../../assembler/masm/elseif-masm.md)または **endif**  などの条件付きアセンブリのディレクティブ。  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)