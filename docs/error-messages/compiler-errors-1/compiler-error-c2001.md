---
title: "コンパイラ エラー C2001 | Microsoft Docs"
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
  - "C2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2001"
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

定数が 2 行目に続いています。  
  
 文字列定数を 2 行目に続ける場合は、次のいずれかの方法を使用してください。  
  
-   1 行目の最後に円記号 \(\\\) を付けます。  
  
-   1 行目の文字列を二重引用符で囲み、次の行の文字列は別の二重引用符で始めます。  
  
 1 行目の最後にエスケープ シーケンス \\n を付けるだけでは不十分です。  
  
## 使用例  
 次の例では警告 C2001 が生成されます。  
  
```  
// C2001.cpp  
// C2001 expected  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,  
             world");  
    printf_s("Hello,\n  
             world");  
}  
```  
  
## 使用例  
 行連結文字の次の行の先頭に置かれた空白文字はすべて文字列定数に含まれます。  上の例では、改行文字は文字列定数に埋め込まれていません。  改行文字を埋め込む例を次に示します。  
  
```  
// C2001b.cpp  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,\n\  
             world");  
  
    printf_s("Hello,\  
             \nworld");  
  
    printf_s("Hello,\n"  
             "world");  
  
    printf_s("Hello,"  
             "\nworld");  
  
    printf_s("Hello,"  
             " world");  
  
    printf_s("Hello,\  
             world");  
}  
```