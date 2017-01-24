---
title: "コンパイラの警告 (レベル 3) C4197 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4197"
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : キャストのトップレベルの volatile は無視されます。  
  
 [volatile](../../cpp/volatile-cpp.md) で修飾された右辺値の型へのキャスト、または volatile で修飾された型への右辺値の型のキャストが見つかりました。  C の標準 \(6.5.3\) では、限定型に関連付けられたプロパティが意味を持つのは、左辺値の式に使用する場合だけです。  
  
 次の例では警告 C4197 が生成されます。  
  
```  
// C4197.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <signal.h>  
#include <stdlib.h>  
  
void sigproc(int);  
struct S  
{  
   int i;  
} s;  
  
int main()  
{  
   signal(SIGINT, sigproc);  
   s.i = 1;  
   S *pS = &s;  
   for ( ; (volatile int)pS->i ; )   // C4197  
      break;  
   // for ( ; *(volatile int *)&pS->i ; )   // OK  
   //    break;  
}  
  
void sigproc(int) // ctrl-C  
{  
   signal(SIGINT, sigproc);  
   s.i = 0;  
}  
  
```