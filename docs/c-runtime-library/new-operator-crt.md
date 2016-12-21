---
title: "演算子 new(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "new[]"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "new[] 演算子"
  - "ベクター型の new"
ms.assetid: 79682f85-6889-40f6-b8f7-9eed5176ea35
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 演算子 new(CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ヒープからメモリ ブロックを割り当てます。  
  
## 構文  
  
```  
  
      void *__cdecl operator new[](size_t count);  
void *__cdecl operator new[] (  
   size_t count,   
   void * object  
) throw();  
void *__cdecl operator new[] (  
   size_t count,   
   const std::nothrow_t&  
) throw();  
```  
  
#### パラメーター  
 *count*  
 割り当てのサイズ。  
  
 *object*  
 オブジェクトが作成されたメモリ ブロックへのポインター。  
  
## 戻り値  
 新しく割り当てられたストレージの最下位バイト アドレスへのポインター。  
  
## 解説  
 `operator new` のこのフォームはスカラー new フォーム \([新しい演算子](../c-runtime-library/operator-new-crt.md)\) とは対照的に、新しいベクターと呼ばれます。  
  
 この演算子の最初のフォームは nonplacement のフォームと呼ばれます。  この演算子の 2 番目のフォームは、配置のフォームと呼ばれ、この演算子の 3 番目のフォームは nonthrowing 配置のフォームです。  
  
 演算子の最初のフォームはコンパイラによって定義され、new.h をプログラムに含まれる必要がありません。  
  
 [&#91;&#93;演算子の削除](../Topic/operator%20delete\(%3Cnew%3E\).md) は 新しい演算子で割り当てられたメモリを解放します。  
  
 `operator new[]` が null を返すか、またはエラーが発生した場合は例外をスローするかどうかを設定できます。  詳細については、「[new および delete 演算子](../cpp/new-and-delete-operators.md)」を参照してください。  
  
 スローするか、非スローする動作を除き、CRT `operator new` は、標準 C\+\+ ライブラリの [新しい演算子&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) と同様に動作します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`new[]`|\<new.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
 次に示すのは、`operator new`ベクターの nonplacement のフォームを使用する方法を示します。  
  
```  
// crt_new4.cpp  
#include <stdio.h>  
int main() {  
   int * k = new int[10];  
   k[0] = 21;  
   printf("%d\n", k[0]);  
   delete [] k;  
}  
```  
  
 次に示すのは、ベクター `operator new`の配置のフォームを使用する方法を示します。  
  
```  
// crt_new5.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * i = new int[10];  
   i[0] = 21;  
   printf("%d\n", i[0]);  
   // initialize existing memory (i) with, in this case, int[[10]  
   int * j = new(i) int[10];   // placement vector new  
   printf("%d\n", j[0]);  
   j[0] = 22;  
   printf("%d\n", i[0]);  
   delete [] i;   // or, could have deleted [] j   
}  
```  
  
 次に示すベクター、配置、`operator new`の非スローのフォームを使用する方法を示します。  
  
```  
// crt_new6.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * k = new(std::nothrow) int[10];  
   k[0] = 21;  
   printf("%d\n", k[0]);  
   delete [] k;  
}  
```  
  
## 参照  
 [メモリ割り当て](../c-runtime-library/memory-allocation.md)