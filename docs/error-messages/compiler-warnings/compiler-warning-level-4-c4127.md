---
title: "コンパイラの警告 (レベル 4) C4127 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4127"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4127"
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 12
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4127
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

条件式が定数です。  
  
 `if` ステートメントまたは `while` ループの制御式が定数に評価されます。 ループが途中で終了するために `while` ループの制御式が定数になる場合は、`while` ループを `for` ループで置き換えることを検討してください。`for` ループの初期化、終了テスト、およびループのインクリメントを省略して、無限ループ \(`while(1)` と同様\) を生じさせる可能性があります。ループは `for` ステートメントの本体から終了できます。  
  
 次の例では C4127 が生成されます。  
  
```  
// C4127.cpp // compile with: /W4 #include <stdio.h> int main() { if (1 == 1) {}   // C4127 while (1) { break; }   // C4127 // OK for ( ; ; ) { printf("test\n"); break; } }  
```