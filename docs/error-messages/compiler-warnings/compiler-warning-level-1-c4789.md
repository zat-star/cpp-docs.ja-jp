---
title: "コンパイラの警告 (レベル 1) C4789 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4789"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4789"
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# コンパイラの警告 (レベル 1) C4789
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バッファー 'identifier' \(サイズが N バイト\) でオーバーランが発生します。M バイトがオフセット L から書き込まれます  
  
 特定の C ランタイム \(CRT\) 関数が使用され、パラメーターが渡され、データ サイズがコンパイル時にわかっているような代入が行われる場合は、バッファー オーバーランについて警告します。  この警告は、一般的なデータ サイズの不一致の検出が回避されるような状況のためのものです。  
  
 コンパイル時に長さがわかっているデータが、コンパイル時にデータに対して小さすぎることがわかっているデータ ブロックにコピーされるときに、警告が表示されます。  コピーは、以下のいずれかの CRT 関数の組み込みの形式を使用して行う必要があります。  
  
-   [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)  
  
-   [memset](../../c-runtime-library/reference/memset-wmemset.md)  
  
-   [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)、[wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)  
  
 キャストの使用でパラメーターのデータ型が不一致になり、左辺値参照からのコピー代入が試みられたときにも、この警告が表示されます。  
  
 Visual C\+\+ では、実行されることのないコード パスに対してこの警告が生成されることがあります。  次の例に示すように、`#pragma` を使用して、警告を一時的に無効にすることができます。  
  
 `#pragma(push)`  
  
 `#pragma warning ( disable : 4789 )`  
  
 `// unused code that generates compiler warning C4789`  
  
 `#pragma(pop)`  
  
 これによって、Visual C\+\+ が特定のコードのブロックに対して警告を生成しないようにすることができます。  `#pragma(push)` は、`#pragma warning(disable: 4789)` によって変更される前に、既存の状態を維持します。  `#pragma(pop)` はプッシュされた状態を復元し、`#pragma warning(disable:4789)` の効果を削除します。  C\+\+ プリプロセッサ ディレクティブ `#pragma` の詳細については、「[warning](../../preprocessor/warning.md)」および「[プラグマ ディレクティブと \_\_Pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。  
  
## 使用例  
 次の例では C4789 が生成されます。  
  
```  
// C4789.cpp  
// compile with: /Oi /W1 /c  
#include <string.h>  
#include <stdio.h>  
  
int main()   
{  
    char a[20];  
    strcpy(a, "0000000000000000000000000\n");   // C4789  
  
    char buf2[20];  
    memset(buf2, 'a', 21);   // C4789  
  
    char c;  
    wchar_t w = 0;  
    memcpy(&c, &w, sizeof(wchar_t));  
}  
```  
  
## 使用例  
 次の例でも C4789 が生成されます。  
  
```  
// C4789b.cpp  
// compile with: /W1 /O2 /c  
// processor: x86  
short G;  
  
void main()  
{  
   int * p = (int *)&G;   
   *p = 3;   // C4789 - writes an int through a pointer to short  
}   
```