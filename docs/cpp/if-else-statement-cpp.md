---
title: "if-else ステートメント (C++) | Microsoft Docs"
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
  - "else_cpp"
  - "else"
  - "if_cpp"
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "else キーワード [C++]"
  - "if キーワード [C++]"
  - "if キーワード [C++], if-else"
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# if-else ステートメント (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

条件分岐を制御します。  
  
## 構文  
  
```  
  
      if ( expression )  
   statement1  
[else  
   statement2]  
```  
  
## 解説  
 *expression* の値がゼロ以外の場合は、*statement1* が実行されます。  オプションの **else** がある場合、*statement2* は *expression* の値がゼロの場合に実行されます。  *expression* は、数値型またはポインター型であるか、数値型またはポインター型への明確な変換を定義するクラス型である必要があります。 変換については、「[標準変換](../cpp/standard-conversions.md)」を参照してください。  
  
 **If** ステートメントの両方の形式で、構造体以外の任意の値を持つことができる *expression* が、すべての副作用を含めて評価されます。  どの*ステートメント*にも [break](../cpp/break-statement-cpp.md)、[continue](../cpp/continue-statement-cpp.md)、または [goto](../cpp/goto-statement-cpp.md) が含まれていない場合は、**if** ステートメントからプログラムの次のステートメントに制御が移ります。  
  
 `if...else` ステートメントの **else** 句は、対応する **else** ステートメントがない同じスコープ内の直前の **If** ステートメントに関連付けられます。  
  
 このサンプルの `if...else` の組み合わせを明確にするには、中かっこのコメントを解除します。  
  
## 使用例  
  
```  
// if_else_statement.cpp  
#include <stdio.h>  
  
int main()   
{  
   int x = 0;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n");  
   }  
   else  
   {  
      printf_s("x is not 0!\n"); // this statement will not be executed  
   }  
  
   x = 1;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n"); // this statement will not be executed  
   }  
   else  
   {  
      printf_s("x is not 0!\n");  
   }  
  
   return 0;  
}  
```  
  
  **x is 0\!**  
**x is not 0\!**   
## 参照  
 [選択ステートメント](../cpp/selection-statements-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [switch ステートメント \(C\+\+\)](../cpp/switch-statement-cpp.md)