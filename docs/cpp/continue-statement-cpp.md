---
title: "continue ステートメント (C++) | Microsoft Docs"
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
  - "continue"
  - "continue_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "continue キーワード [C++]"
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# continue ステートメント (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

外側にある最小の [do](../cpp/do-while-statement-cpp.md)、[for](../cpp/for-statement-cpp.md)、または [while](../cpp/while-statement-cpp.md) ループの制御式に強制的に制御を移します。  
  
## 構文  
  
```  
continue;  
```  
  
## 解説  
 現在のイテレーションの残りのステートメントは実行されません。  ループの次のイテレーションは、次のように決定されます。  
  
-   `do` または `while` ループ内では、次のイテレーションは `do` または `while` ステートメントの制御式を再評価することによって開始されます。  
  
-   `for` ループ \(構文 `for`\(`init-expr`; `cond-expr`; `loop-expr`\) を使用\) では、`loop-expr` 句が実行されます。  次に、`cond-expr` 句が再評価され、その結果に応じて、ループが終了するか、別のイテレーションが発生します。  
  
 次の例は、`continue` ステートメントを使用してコードのセクションをバイパスし、ループの次のイテレーションを開始する方法を示しています。  
  
## 使用例  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
  **before the continue**  
**before the continue**  
**before the continue**  
**after the do loop**   
## 参照  
 [ジャンプ ステートメント](../cpp/jump-statements-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)