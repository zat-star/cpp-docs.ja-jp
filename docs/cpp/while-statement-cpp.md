---
title: "while ステートメント (C++) | Microsoft Docs"
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
  - "while_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "while キーワード [C++]"
  - "while キーワード [C++], 構文"
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# while ステートメント (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*expression* がゼロになるまで *statement* を繰り返し実行します。  
  
## 構文  
  
```  
  
      while ( expression )  
   statement  
```  
  
## 解説  
 *expression* が評価されてからループが実行されるので、`while` ループは 0 回以上実行されます。  *expression* は、整数またはポインター型への明確な変換を使用した整数型、ポインター型、またはクラス型である必要があります。  
  
 `while` ループは、[break](../cpp/break-statement-cpp.md)、[goto](../cpp/goto-statement-cpp.md)、または [return](../Topic/return%20Statement%20\(C++\).md) がステートメント本体で実行されたときにも終了できます。  `while` ループを終了せずに現在の反復を終了するには、[continue](../cpp/continue-statement-cpp.md) を使用します。  **continue** は `while` ループの次のイテレーションに制御を渡します。  
  
 次のコードは、文字列の末尾のアンダースコアをトリミングするために `while` ループを使用します。  
  
```  
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 終了条件はループの先頭で評価されます。  末尾のアンダースコアがない場合、ループは実行されません。  
  
## 参照  
 [繰り返しステートメント](../cpp/iteration-statements-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [do\-while ステートメント \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [for ステートメント \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [範囲ベースの for ステートメント \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md)