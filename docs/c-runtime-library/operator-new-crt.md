---
title: "new 演算子 (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "new 演算子"
  - "スカラー new"
ms.assetid: 4ae51618-a4e6-4172-b324-b99d86d1bdca
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# new 演算子 (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ヒープからメモリ ブロックを割り当てます。  
  
## 構文  
  
```  
  
      void *__cdecl operator new(  
   size_t count  
);  
void *__cdecl operator new(  
   size_t count,   
   void * object  
) throw();  
void *__cdecl operator new(  
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
 `operator new` のこのフォームはベクターの新しいフォーム \([新しい演算子&#91;&#93;](../c-runtime-library/new-operator-crt.md)\) とは対照的スカラー new と呼びます。  
  
 この演算子の最初のフォームは nonplacement のフォームと呼ばれます。  この演算子の 2 番目のフォームは、配置のフォームと呼ばれ、この演算子の 3 番目のフォームは nonthrowing の配置のフォームです。  
  
 演算子の最初のフォームはコンパイラによって定義され、new.h をプログラムに含まれる必要がありません。  
  
 [演算子の削除](../c-runtime-library/operator-delete-crt.md) は `operator new`で割り当てられたメモリを解放します。  
  
 演算子の新しい制御が無効に設定するか、または失敗かどうかの例外をスローします。  詳細については、「[new および delete 演算子](../cpp/new-and-delete-operators.md)」を参照してください。  
  
 スローするか、非スローする動作を除き、CRT `operator new` は、標準 C\+\+ ライブラリの [新しい演算子](../Topic/operator%20new%20\(%3Cnew%3E\).md) と同様に動作します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|**new**|\<new.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
 次に示すスカラー、`operator new`の nonplacement のフォームを使用する方法を示します。  
  
```  
// crt_new1.cpp  
#include <stdio.h>  
int main() {  
   int * i = new int(6);  
   printf("%d\n", *i);  
   delete i;  
}  
```  
  
 次に示すスカラー、`operator new`の配置のフォームを使用する方法を示します。  
  
```  
// crt_new2.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * i = new int(12);  
   printf("*i = %d\n", *i);  
   // initialize existing memory (i) with, in this case, int(7)  
   int * j = new(i) int(7);   // placement new  
   printf("*j = %d\n", *j);  
   printf("*i = %d\n", *i);  
   delete i;   // or, could have deleted j  
}  
```  
  
 次に示すスカラー、配置、`operator new`の非スローのフォームを使用する方法を示します。  
  
```  
// crt_new3.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   // allocates memory, initialize (8) and if call fails, new returns null  
   int * k = new(std::nothrow) int(8);   // placement new  
   printf("%d\n", *k);  
   delete k;  
}  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../c-runtime-library/memory-allocation.md)