---
title: "_freea | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_freea"
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
apitype: "DLLExport"
f1_keywords: 
  - "freea"
  - "_freea"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_freea 関数"
  - "freea 関数"
  - "メモリ解放"
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _freea
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メモリ ブロックを解放するか、解放します。  
  
## 構文  
  
```  
void _freea(   
   void *memblock   
);  
```  
  
#### パラメーター  
 `memblock`  
 以前は解放される割り当てられたメモリ ブロック。  
  
## 戻り値  
 なし。  
  
## 解説  
 `_freea`関数は [\_malloca](../../c-runtime-library/reference/malloca.md)の呼び出しにより前に割り当てられたメモリ ブロック \(`memblock`\) を解放します。  `_freea` は メモリをヒープまたはスタックに割り当てられているかどうかを確認します。  これがスタックに割り当てられている場合、`_freea` は機能しません。  これがヒープに割り当てられ、解放されたバイト数はブロックを割り当てるときに要求されたバイト数と同じです。  `memblock` が `NULL`の場合、ポインターは無視され、`_freea` が直ちに返されます。  無効なポインター \(`_malloca`でないメモリ ブロックへのポインター\) を解放しようとすると、それ以降の割り当て要求に影響し、エラーが発生することがあります。  
  
 メモリをヒープに割り当てられたことが検出された場合は`freea` は `free` を内部的に呼び出します。  メモリをヒープまたはスタックであるかに割り当てられたメモリのアドレスはメモリ内にあるマーカーによって決まります。  
  
 メモリの解放でエラーが発生すると、エラーの性質に関するオペレーティング システムからの情報が `errno` に設定されます。  詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 メモリ ブロックが解放されると、[\_heapmin](../../c-runtime-library/reference/heapmin.md) は結合し、オペレーティング システムにおいて、を解放することによって、未使用のメモリ ヒープ領域の量を最小限に抑えることができます。  オペレーティング システムに解放されない解放されたメモリは空きプールに復元し、割り当てに再利用できます。  
  
 `_freea` の呼び出しは `_malloca`へのすべての呼び出しに伴わなければ必要があります。  また、同じメモリの `_freea` を二度呼び出すエラーです。  アプリケーションが C ランタイム ライブラリのデバッグ バージョンとリンクすると、特に [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md) 機能と `_CRTDBG_MAP_ALLOC`の定義で有効になっている `_freea`にパーツが見つからないか、重複している呼び出しを見つけやすくなります。  ヒープのデバッグ中にどのように管理されるかを詳細については、「[CRT のデバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  
  
 `_freea` は グローバル変数を変更せずに関数が保証されることを意味するマークされた `__declspec(noalias)`です。  詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_freea`|\<stdlib.h\> および \<malloc.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [\_malloca](../../c-runtime-library/reference/malloca.md) 関数の例を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [\_malloca](../../c-runtime-library/reference/malloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)