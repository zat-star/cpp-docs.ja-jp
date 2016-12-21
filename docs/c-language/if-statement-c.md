---
title: "if ステートメント (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "else"
  - "if"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "else 句"
  - "else キーワード [C]"
  - "if キーワード [C]"
  - "if キーワード [C], if ステートメント構文"
  - "入れ子になったステートメント"
ms.assetid: d7fc16a0-fdbc-4f39-b596-76e1ca4ad4a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# if ステートメント (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**If** ステートメントは、条件分岐を制御します。  **if** ステートメントの本体は、式の値が 0 でないの場合に実行されます。  **if** ステートメントの構文には 2 とおりの形式があります。  
  
## 構文  
 *selection\-statement*:  
 **if \(**  *expression*  **\)**  *statement*  
  
 **if \(**  *式*  **\)**  *ステートメント*  **else**  *ステートメント*  
  
 **If** ステートメントの両方の形式で、構造体以外のすべての値を持つことができる式が、すべての副作用を含めて評価されます。  
  
 最初の構文では、*expression* が true \(0 以外\) の場合、*statement* が実行されます。  式が false の場合、ステートメントは無視されます。  **else** を使用する 2 番目の構文形式では、*expression* が false の場合、2 番目の *statement* が実行されます。  どちらの形式でも、いずれかのステートメントに **break**、**continue**、または `goto` が含まれていない場合は、制御が **if** ステートメントからプログラムの次のステートメントに移ります。  
  
 **if** ステートメントの例を次に示します。  
  
```  
if ( i > 0 )  
    y = x / i;  
else   
{  
    x = i;  
    y = f( x );  
}  
```  
  
 この例では、ステートメント本体 `y = x/i;` は、`i` が 0 を超える場合に実行されます。  `i` が 0 以下の場合、`i` が `x` に割り当てられ、`f( x )` が `y` に割り当てられます。  **if** 句を形成するステートメントはセミコロンで終わることに注意してください。  
  
 **if** ステートメントと **else** 句を入れ子にする場合は、意図がはっきりわかるように、中かっこを使用してステートメントと句を複合ステートメントにグループ化します。  中かっこがない場合、コンパイラは各 **else** を **else** のない最も近い **If** と関連付けることで、あいまいさを解消します。  
  
```  
if ( i > 0 )           /* Without braces */  
    if ( j > i )  
        x = j;  
    else  
        x = i;  
```  
  
 **else** 句は、この例の内側の **If** ステートメントに関連付けられます。  `x` が 0 以下の場合、`i` に値は割り当てられません。  
  
```  
if ( i > 0 )   
{                      /* With braces */  
    if ( j > i )  
        x = j;  
}  
else  
    x = i;  
```  
  
 この例の内側の **if** ステートメントを囲んでいる中かっこにより、**else** 句は外側の **if** ステートメントの一部になります。  `i` が 0 以下の場合、`i` が `x` に割り当てられます。  
  
## 参照  
 [if\-else ステートメント \(C\+\+\)](../cpp/if-else-statement-cpp.md)