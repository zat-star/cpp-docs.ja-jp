---
title: "_calloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_calloc_dbg"
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
  - "_calloc_dbg"
  - "calloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_calloc_dbg 関数"
  - "calloc_dbg 関数"
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _calloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

デバッグ ヘッダーと上書きバッファー用の追加の領域を持つ多数のメモリ ブロックをヒープに割り当てます \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
void *_calloc_dbg(   
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### パラメーター  
 `num`  
 要求するメモリ ブロックの数。  
  
 `size`  
 要求する各メモリ ブロックのサイズ \(バイト\)。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインター、または `NULL`。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または `NULL`。  
  
 `filename` パラメーターと `linenumber` パラメーターを使用できるのは、`_calloc_dbg` が明示的に呼び出された場合、または [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) プリプロセッサ定数が定義されている場合だけです。  
  
## 戻り値  
 正常に終了した場合、この関数は最後に割り当てられたメモリ ブロックのユーザー部分へのポインターを返すか、新しいハンドラー関数を呼び出すか、`NULL` を返します。  戻る動作の詳細については、「解説」のセクションを参照してください。  新しいハンドラー関数がどのように使用されるかの詳細については、[calloc](../../c-runtime-library/reference/calloc.md) 関数を参照してください。  
  
## 解説  
 `_calloc_dbg` は、[calloc](../../c-runtime-library/reference/calloc.md) 関数のデバッグ バージョンです。  [\_DEBUG](../Topic/_DEBUG.md) が定義されない場合、`_calloc_dbg` への各呼び出しは `calloc` への呼び出しになります。  `calloc` と `_calloc_dbg` は、どちらもベース ヒープに `num` 個のメモリ ブロックを割り当てますが、`_calloc_dbg` は次のようないくつかのデバッグ機能を提供します。  
  
-   リークをテストするための、ブロックのユーザー部分の両側のバッファー。  
  
-   特定の割り当ての種類を追跡するためのブロック型パラメーター。  
  
-   割り当て要求の起点を特定するための `filename`\/`linenumber` 情報。  
  
 `_calloc_dbg` は、要求された `size` よりも少し多い領域を使用して各メモリ ブロックを割り当てます。  追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。  ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。  
  
 メモリ割り当てが失敗すると、`_calloc_dbg` は `errno` を `ENOMEM` に設定します。必要なメモリの量 \(前に説明したオーバーヘッドを含む\) が `_HEAP_MAXREQ` を超えると、`EINVAL` が返されます。  エラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法の詳細については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  アプリケーションのデバッグ ビルドで標準ヒープ関数を呼び出す場合とデバッグ バージョンを呼び出す場合との違いについては、「[デバッグ バージョンのヒープ割り当て関数](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_calloc_dbg`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_callocd.c  
/*  
 * This program uses _calloc_dbg to allocate space for  
 * 40 long integers. It initializes each element to zero.  
 */  
#include <stdio.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
        long *bufferN, *bufferC;  
  
        /*   
         * Call _calloc_dbg to include the filename and line number  
         * of our allocation request in the header and also so we can  
         * allocate CLIENT type blocks specifically  
         */  
        bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );  
        if( bufferN != NULL && bufferC != NULL )  
              printf( "Allocated memory successfully\n" );  
        else  
              printf( "Problem allocating memory\n" );  
  
        /*   
         * _free_dbg must be called to free CLIENT type blocks  
         */  
        free( bufferN );  
        _free_dbg( bufferC, _CLIENT_BLOCK );  
}  
```  
  
  **Allocated memory successfully**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [\_DEBUG](../Topic/_DEBUG.md)