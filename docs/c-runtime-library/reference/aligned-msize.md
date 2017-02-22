---
title: "_aligned_msize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_msize"
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
  - "_aligned_msize"
  - "aligned_msize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_msize 関数"
  - "aligned_msize 関数"
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _aligned_msize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープに割り当てられたメモリ ブロックのサイズを返します。  
  
## 構文  
  
```  
size_t _msize(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### パラメーター  
 \[入力\] `memblock`  
 メモリ ブロックへのポインター。  
  
 \[入力\] `alignment`  
 アラインメント値。2 の整数乗である必要があります。  
  
 \[入力\] `offset`  
 アラインメントを強制するためのメモリ割り当てへのオフセット。  
  
## 戻り値  
 符号なし整数としてサイズ \(バイト数\) を返します。  
  
## 解説  
 [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_realloc](../../c-runtime-library/reference/aligned-realloc.md)への `_aligned_msize` 関数の戻り値はサイズ、呼び出しによって割り当てられたメモリ ブロックのサイズ \(バイト単位\)。  `alignment` と `offset` の値は、ブロックを割り当てた関数に渡される値と同じである必要があります。  
  
 アプリケーションが C ランタイム ライブラリのデバッグ バージョンとリンクすると、`_aligned_msize` は [\_aligned\_msize\_dbg](../../c-runtime-library/reference/aligned-msize-dbg.md)に解決されます。  ヒープのデバッグ中にどのように管理されるかを詳細については、「[CRT のデバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  
  
 この関数は、そのパラメーターを検証します。  `memblock` が null ポインターであるか `alignment` が 2 の累乗でない場合、`_msize` は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。  エラーが処理されると、`errno` が `EINVAL` に設定され、\-1 が返されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_msize`|\<malloc.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)