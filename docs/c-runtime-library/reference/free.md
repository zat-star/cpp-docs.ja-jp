---
title: "free | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "free"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "free"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メモリ ブロック、解放"
  - "free 関数"
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メモリ ブロックを解放するか、解放します。  
  
## 構文  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### パラメーター  
 `memblock`  
 以前は解放される割り当てられたメモリ ブロック。  
  
## 解説  
 `free` 関数は `calloc`、`malloc`、または `realloc`の呼び出しにより前に割り当てられたメモリ ブロック \(`memblock`\) を解放します。  解放されたバイト数はブロックを割り当てるときに要求されたバイト数に相当します \(または、`realloc`の場合は再割り当てされます\)。  `memblock` が `NULL`の場合、ポインターは無視され、`free` が直ちに返されます。  無効なポインター \(`calloc`でないメモリ ブロック、`malloc`、または `realloc`へのポインター\) を解放しようとすると、それ以降の割り当て要求に影響し、エラーが発生することがあります。  
  
 メモリの解放でエラーが発生すると、エラーの性質に関するオペレーティング システムからの情報が `errno` に設定されます。  詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 メモリ ブロックが解放されると、[\_heapmin](../../c-runtime-library/reference/heapmin.md) は結合し、オペレーティング システムにおいて、を解放することによって、未使用のメモリ ヒープ領域の量を最小限に抑えることができます。  オペレーティング システムに解放されない解放されたメモリは空きプールに復元し、割り当てに再利用できます。  
  
 アプリケーションが C ランタイム ライブラリのデバッグ バージョンとリンクすると、`free` は [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)に解決されます。  ヒープのデバッグ中にどのように管理されるかを詳細については、「[CRT のデバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  
  
 `free` は グローバル変数を変更せずに関数が保証されることを意味するマークされた `__declspec(noalias)`です。  詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。  
  
 [\_malloca](../../c-runtime-library/reference/malloca.md)に割り当てられたメモリを [\_freea](../../c-runtime-library/reference/freea.md)を使用します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`free`|\<stdlib.h\> および \<malloc.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [malloc](../../c-runtime-library/reference/malloc.md)"の例を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [\_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_freea](../../c-runtime-library/reference/freea.md)