---
title: "_aligned_msize_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_msize_dbg"
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
  - "_aligned_msize_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_msize_dbg"
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_msize_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープで割り当てられたメモリ ブロックのサイズを返します \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
size_t _aligned_msize_dbg(  
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
 `alignment` と `offset` の値は、ブロックを割り当てた関数に渡される値と同じである必要があります。  
  
 `_aligned_msize_dbg` は、[\_aligned\_msize](../../c-runtime-library/reference/aligned-msize.md) 関数のデバッグ バージョンです。  [\_DEBUG](../Topic/_DEBUG.md) が定義されない場合、`_aligned_msize_dbg` への各呼び出しは `_aligned_msize` への呼び出しになります。  `_aligned_msize` と `_aligned_msize_dbg` は、どちらもベース ヒープ内のメモリ ブロックのサイズを計算しますが、`_aligned_msize_dbg` はデバッグ機能を追加します。そのため、返されるサイズに、メモリ ブロックのユーザー部分の両側のバッファーが含められます。  
  
 この関数は、そのパラメーターを検証します。  `memblock` が null ポインターであるか `alignment` が 2 の累乗でない場合、`_msize` は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。  エラーが処理されると、`errno` が `EINVAL` に設定され、\-1 が返されます。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法の詳細については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  アプリケーションのデバッグ ビルドで標準ヒープ関数を呼び出す場合とデバッグ バージョンを呼び出す場合との違いについては、「[デバッグ バージョンのヒープ割り当て関数](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_aligned_msize_dbg`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)