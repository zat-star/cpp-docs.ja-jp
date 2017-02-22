---
title: "_aligned_realloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_realloc_dbg"
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
  - "aligned_realloc_dbg"
  - "_aligned_realloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_realloc_dbg 関数"
  - "aligned_realloc_dbg 関数"
ms.assetid: 8aede920-991e-44cd-867f-83dc2165db47
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_realloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリ ブロックのサイズを変更します \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
void * _aligned_realloc_dbg(    void *memblock,     size_t size,     size_t alignment,    const char *filename,    int linenumber  );  
```  
  
#### パラメーター  
 \[入力\] `memblock`  
 現在のメモリ ブロック ポインター。  
  
 \[入力\] `size`  
 要求されたメモリ割り当てのサイズ。  
  
 \[入力\] `alignment`  
 アラインメント値。2 の整数乗である必要があります。  
  
 \[入力\] `filename`  
 `realloc` 操作を要求したソース ファイル名へのポインター、または NULL。  
  
 \[入力\] `linenumber`  
 `realloc` 操作が要求されたソース ファイル内の行番号または NULL。  
  
## 戻り値  
 `_aligned_realloc_dbg` は、再割り当てされた \(移動された可能性もある\) メモリ ブロックへの void ポインターを返します。  サイズが 0 でバッファー引数が `NULL` ではない場合、または特定のサイズにブロックを拡張するのに十分なメモリを使用できない場合、戻り値は `NULL` です。  最初の場合には、元のブロックは解放されます。  2 番目の場合には、元のブロックは変更されません。  戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。  void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。  
  
 メモリを再割り当てしてブロックのアラインメントを変更すると、エラーになります。  
  
## 解説  
 `_aligned_realloc_dbg` は、[\_aligned\_realloc](../../c-runtime-library/reference/aligned-realloc.md) 関数のデバッグ バージョンです。  [\_DEBUG](../Topic/_DEBUG.md) が定義されない場合、`_aligned_realloc_dbg` への各呼び出しは \_`aligned_realloc` への呼び出しになります。  \_`aligned_realloc` と `_aligned_realloc_dbg` はベース ヒープ内にメモリ ブロックを再割り当てしますが、`_aligned_realloc_dbg` はいくつかのデバッグ機能を提供します。たとえば、リークをテストするための、ブロックのユーザー部分の両側のバッファー、特定の割り当ての種類を追跡するためのブロック型パラメーター、割り当て要求の起点を特定するための `filename`\/`linenumber` 情報などです。  
  
 `_aligned_realloc_dbg` は、要求された `newSize` よりも少し多い領域を使用して指定されたメモリ ブロックを再割り当てします。  `newSize` は、最初に割り当てられたメモリ ブロックのサイズより大きくなったり小さくなったりする場合があります。  追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。  再割り当てによって、元のメモリ ブロックがヒープ内の別の位置に移動されたり、メモリ ブロックのサイズが変わったりする場合があります。  メモリ ブロックが移動される場合、元のブロックの内容は上書きされます。  
  
 メモリ割り当てが失敗するか、必要なメモリの量 \(前に説明したオーバーヘッドを含む\) が `_HEAP_MAXREQ` を超えると、`_aligned_realloc_dbg` は `errno` を `ENOMEM` に設定します。  エラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 また、`_aligned_realloc_dbg` はそのパラメーターを検証します。  `alignment` が 2 の累乗でない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数によって無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、この関数は `NULL` を返し、`errno` を `NULL` に設定します。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法の詳細については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  割り当てブロックの種類とそれらの使用方法の詳細については、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  アプリケーションのデバッグ ビルドで標準ヒープ関数を呼び出す場合とデバッグ バージョンを呼び出す場合との違いについては、「[デバッグ バージョンのヒープ割り当て関数](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_aligned_realloc_dbg`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)