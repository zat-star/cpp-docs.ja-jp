---
title: "function (C/C++) | Microsoft Docs"
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
  - "function_CPP"
  - "vc-pragma.function"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "function プラグマ"
  - "プラグマ, 関数"
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
caps.latest.revision: 10
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# function (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このプラグマの引数リストで指定された関数を呼び出します。  
  
## 構文  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## 解説  
 **intrinsic** プラグマ \(または \/Oi\) を使用し、組み込み関数を生成するようコンパイラに指示する場合 \(組み込み関数は、関数呼び出しではなく、インライン コードとして生成されます\)、**function** プラグマを使用すれば、関数呼び出しを明示的に適用できます。  コンパイラが function プラグマを検出した後、組み込み関数を含む最初の関数定義に達した時点でそのプラグマが有効になります。  その後、function プラグマの効果は、ソース ファイルの最後まで、または同じ組み込み関数を指定した **intrinsic** プラグマが検出されるまで持続します。  **function** プラグマは、関数の外側でのみ \(グローバル レベルで\) 使用できます。  
  
 組み込み形式を持つ関数の一覧は、「[\#pragma intrinsic](../preprocessor/intrinsic.md)」を参照してください。  
  
## 使用例  
  
```  
// pragma_directive_function.cpp  
#include <ctype.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
  
// use intrinsic forms of memset and strlen  
#pragma intrinsic(memset, strlen)  
  
// Find first word break in string, and set remaining  
// chars in string to specified char value.  
char *set_str_after_word(char *string, char ch) {  
   int i;  
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */  
  
   for(i = 0; i < len; i++) {  
      if (isspace(*(string + i)))   
         break;  
   }  
  
   for(; i < len; i++)   
      *(string + i) = ch;  
  
   return string;  
}  
  
// do not use strlen intrinsic  
#pragma function(strlen)  
  
// Set all chars in string to specified char value.  
char *set_str(char *string, char ch) {  
   // Uses intrinsic for memset, but calls strlen library function  
   return (char *) memset(string, ch, strlen(string));  
}  
  
int main() {  
   char *str = (char *) malloc(20 * sizeof(char));  
  
   strcpy_s(str, sizeof("Now is the time"), "Now is the time");  
   printf("str is '%s'\n", set_str_after_word(str, '*'));  
   printf("str is '%s'\n", set_str(str, '!'));  
}  
```  
  
  **str is 'Now\*\*\*\*\*\*\*\*\*\*\*\*'**  
**str is '\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!'**   
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)