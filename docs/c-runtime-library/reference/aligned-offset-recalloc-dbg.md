---
title: "_aligned_offset_recalloc_dbg | Microsoft Docs"
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
  - "_aligned_offset_recalloc_dbg"
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
  - "aligned_offset_recalloc_dbg"
  - "_aligned_offset_recalloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_offset_recalloc_dbg 関数"
  - "aligned_offset_recalloc_dbg 関数"
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_recalloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリ ブロックのサイズを変更し、メモリを 0 に初期化します \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
void * _aligned_offset_recalloc_dbg(    void *memblock,     size_t num,     size_t size,     size_t alignment,    size_t offset,    const char *filename,    int linenumber );  
```  
  
#### パラメーター  
 \[入力\] `memblock`  
 現在のメモリ ブロック ポインター。  
  
 \[入力\] `num`  
 要素の数。  
  
 \[入力\] `size`  
 各要素の長さ \(バイト単位\)。  
  
 \[入力\] `alignment`  
 アラインメント値。2 の整数乗である必要があります。  
  
 \[入力\] `offset`  
 アラインメントを強制するためのメモリ割り当てへのオフセット。  
  
 \[入力\] `filename`  
 `realloc` 操作を要求したソース ファイル名へのポインター、または NULL。  
  
 \[入力\] `linenumber`  
 `realloc` 操作が要求されたソース ファイル内の行番号または NULL。  
  
## 戻り値  
 `_aligned_offset_recalloc_dbg` は、再割り当てされた \(移動された可能性もある\) メモリ ブロックへの void ポインターを返します。  サイズが 0 でバッファー引数が `NULL` ではない場合、または特定のサイズにブロックを拡張するのに十分なメモリを使用できない場合、戻り値は `NULL` です。  最初の場合には、元のブロックは解放されます。  2 番目の場合には、元のブロックは変更されません。  戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。  void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。  
  
## 解説  
 `_aligned_offset_realloc_dbg` は、[\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md) 関数のデバッグ バージョンです。  [\_DEBUG](../Topic/_DEBUG.md) が定義されない場合、`_aligned_offset_recalloc_dbg` への各呼び出しは \_`aligned_offset_recalloc` への呼び出しになります。  \_`aligned_offset_recalloc` と `_aligned_offset_recalloc_dbg` はベース ヒープ内にメモリ ブロックを再割り当てしますが、`_aligned_offset_recalloc_dbg` はいくつかのデバッグ機能を提供します。たとえば、リークをテストするための、ブロックのユーザー部分の両側のバッファー、特定の割り当ての種類を追跡するためのブロック型パラメーター、割り当て要求の起点を特定するための `filename`\/`linenumber` 情報などです。  
  
 `_aligned_offset_realloc_dbg` は、要求された `newSize` よりも少し多い領域を使用して指定されたメモリ ブロックを再割り当てします。  `newSize` は、最初に割り当てられたメモリ ブロックのサイズより大きくなったり小さくなったりする場合があります。  追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。  再割り当てによって、元のメモリ ブロックがヒープ内の別の位置に移動されたり、メモリ ブロックのサイズが変わったりする場合があります。  メモリ ブロックが移動される場合、元のブロックの内容は上書きされます。  
  
 この関数は、メモリ割り当てが失敗するか、要求されたサイズ \(`num` \* `size`\) が `_HEAP_MAXREQ` より大きかった場合に、`errno` を `ENOMEM` に設定します。  `errno` の詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  また、`_aligned_offset_recalloc_dbg` はそのパラメーターを検証します。  `alignment` が 2 の累乗でないか、`offset` が要求されたサイズ以上かつ 0 以外である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `NULL` を返し、`errno` を `NULL` に設定します。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法の詳細については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  割り当てブロックの種類とそれらの使用方法の詳細については、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  アプリケーションのデバッグ ビルドで標準ヒープ関数を呼び出す場合とデバッグ バージョンを呼び出す場合との違いについては、「[デバッグ バージョンのヒープ割り当て関数](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_aligned_offset_recalloc_dbg`|\<malloc.h\>|  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [データの整列](../../c-runtime-library/data-alignment.md)