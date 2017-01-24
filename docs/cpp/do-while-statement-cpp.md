---
title: "do-while ステートメント (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "do-while_cpp"
  - "do-while"
  - "do"
  - "while_cpp"
  - "do_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "do キーワード [C++]"
  - "do キーワード [C++], do-while"
  - "do-while キーワード [C++]"
  - "while キーワード [C++], do-while"
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# do-while ステートメント (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した終了条件 \(*expression*\) がゼロになるまで *statement* を繰り返し実行します。  
  
## 構文  
  
```  
  
      do  
   statement  
   while ( expression ) ;  
```  
  
## 解説  
 終了条件のテストは、ループの各実行の後で行われます。したがって、`do-while` ループは終了式の値に応じて 1 回以上実行されます。  `do-while` ステートメントは、[break](../cpp/break-statement-cpp.md)、[goto](../cpp/goto-statement-cpp.md)、または [return](../Topic/return%20Statement%20\(C++\).md) ステートメントがステートメントの本体で実行されたときにも終了できます。  
  
 *expression* は演算型またはポインター型であることが必要です。  次のように実行されます。  
  
1.  ステートメントの本体が実行されます。  
  
2.  次に、*expression* が評価されます。  *expression* が false の場合、`do-while` ステートメントが終了し、制御はプログラムの次のステートメントに渡されます。  *expression* が true \(0 以外\) の場合、プロセスは手順 1 から繰り返されます。  
  
## 使用例  
 次のコードは、`do-while` ステートメントの使用例です。  
  
```  
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## 参照  
 [繰り返しステートメント](../cpp/iteration-statements-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [while ステートメント \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [for ステートメント \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [範囲ベースの for ステートメント \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md)