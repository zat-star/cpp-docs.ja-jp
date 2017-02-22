---
title: "_malloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_malloc_dbg"
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
  - "malloc_dbg"
  - "_malloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_malloc_dbg 関数"
  - "malloc_dbg 関数"
  - "メモリの割り当て"
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _malloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

デバッグ ヘッダーと上書きバッファー用の追加の領域を持つメモリ ブロックをヒープに割り当てます \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
void *_malloc_dbg(    size_t size,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### パラメーター  
 `size`  
 要求するメモリ ブロックのサイズ \(バイト単位\)。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインターまたは NULL。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または NULL。  
  
 `filename` パラメーターと `linenumber` パラメーターを使用できるのは、`_malloc_dbg` が明示的に呼び出された場合、または [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) プリプロセッサ定数が定義されている場合だけです。  
  
## 戻り値  
 正常に終了した場合、この関数は割り当てられたメモリ ブロックのユーザー部分へのポインターを返すか、新しいハンドラー関数を呼び出すか、NULL を返します。  戻る動作の詳細については、後の「解説」のセクションを参照してください。  新しいハンドラー関数がどのように使用されるかの詳細については、[malloc](../../c-runtime-library/reference/malloc.md) 関数を参照してください。  
  
## 解説  
 `_malloc_dbg` は、[malloc](../../c-runtime-library/reference/malloc.md) 関数のデバッグ バージョンです。  [\_DEBUG](../Topic/_DEBUG.md) が定義されない場合、`_malloc_dbg` への各呼び出しは `malloc` への呼び出しになります。  `malloc` と `_malloc_dbg` はベース ヒープ内にメモリ ブロックを割り当てますが、`_malloc_dbg` はいくつかのデバッグ機能を提供します。たとえば、リークをテストするための、ブロックのユーザー部分の両側のバッファー、特定の割り当ての種類を追跡するためのブロック型パラメーター、割り当て要求の起点を特定するための `filename`\/`linenumber` 情報などです。  
  
 `_malloc_dbg` は、要求された `size` よりも少し多い領域を使用してメモリ ブロックを割り当てます。  追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。  ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。  
  
 メモリ割り当てが失敗するか、必要なメモリの量 \(前に説明したオーバーヘッドを含む\) が `_HEAP_MAXREQ` を超えると、`_malloc_dbg` は `errno` を `ENOMEM` に設定します。  エラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法の詳細については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  割り当てブロックの種類とそれらの使用方法の詳細については、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  アプリケーションのデバッグ ビルドで標準ヒープ関数を呼び出す場合とデバッグ バージョンを呼び出す場合との違いについては、「[デバッグ バージョンのヒープ割り当て関数](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_malloc_dbg`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## 使用例  
 `_malloc_dbg` の使用例については、「[crt\_dbg1](http://msdn.microsoft.com/ja-jp/17b4b20c-e849-48f5-8eb5-dca6509cbaf9)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md)   
 [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md)