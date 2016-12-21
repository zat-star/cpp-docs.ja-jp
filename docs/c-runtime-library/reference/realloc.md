---
title: "realloc | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "realloc"
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
  - "_brealloc"
  - "_nrealloc"
  - "realloc"
  - "_frealloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_brealloc 関数"
  - "realloc 関数"
  - "nrealloc 関数"
  - "frealloc 関数"
  - "_nrealloc 関数"
  - "メモリ ブロック、再割り当て"
  - "メモリ、再割り当て"
  - "_frealloc 関数"
  - "再割り当て (メモリ ブロックを)"
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メモリ ブロックを再割り当てします。  
  
## 構文  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### パラメーター  
 `memblock`  
 前に割り当てられたメモリ ブロックへのポインター。  
  
 `size`  
 バイトの新しいサイズ。  
  
## 戻り値  
 `realloc` が 再割り当てされる場合 \(移動\) メモリ ブロックの `void` のポインターを返します。  
  
 特定のサイズにブロックを展開する十分な使用可能なメモリがある元のブロックは変更されず、`NULL` が返されます。  
  
 `size` がゼロの場合、`memblock` が指す;ブロックが解放されます。戻り値は `NULL`であり、`memblock` は解放されたブロックの指を保持されます。  
  
 戻り値は適切にどの型のオブジェクトを格納するために配置されることが保証されるストレージ領域を指します。  `void`以外の型へのポインターを取得するには、戻り値の型キャストを使用してください。  
  
## 解説  
 `realloc` の関数の変更に割り当てられたメモリ ブロックのサイズ。  `memblock` の引数はメモリ ブロックの開始を示します。  `memblock` が `NULL`の場合、`realloc` は `malloc` と同様に動作し、`size` バイトの新しいブロックを割り当てます。  `memblock` が `NULL`でない場合、`calloc`、`malloc`、または `realloc`に前の呼び出しによって返されるポインターのようになります。  
  
 `size` の引数はバイト ブロックの新しいサイズが表示されます。  ブロックの内容が新しいブロックが別の場所に存在する場合もありますが、新しい古いサイズの短いのまで変更できません。  新しいブロックは新しいメモリ位置にあるため `realloc` で返されたポインターは `memblock` 引数を介して渡されたポインターであることは保証されません。  `realloc` は バッファー増加で新しく割り当てられたメモリをゼロになります。  
  
 `realloc` は `ENOMEM` にメモリ割り当てが失敗した場合、または要求されているメモリの量を `_HEAP_MAXREQ`を超えた場合 `errno` を設定します。  これにより、およびそのほかのエラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 `realloc`の呼び出し `malloc`C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 関数を new ハンドラー モードを設定するために使用します。  新しいハンドラー モードは、エラーが発生したときに、`malloc` が [\_set\_new\_handler](../Topic/_set_new_handler.md) によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。  既定では、`malloc` は、メモリの割り当てエラーの際に新しいハンドラー ルーチンを呼び出しません。  この既定の動作をオーバーライドすると、`realloc` がメモリの割り当てに失敗したときに、`new` 演算子が同じ理由で失敗したときと同じ方法で、`malloc` によって新しいハンドラー ルーチンを呼び出すことができます。  既定の動作をオーバーライドするには、次の関数を呼び出します。  
  
```  
_set_new_mode(1)  
```  
  
 前のプログラム、または NEWMODE.OBJ のリンク \([リンク オプション](../Topic/Link%20Options.md)を参照してください。  
  
 アプリケーションが C ランタイム ライブラリのデバッグ バージョンとリンクすると、`realloc` は [\_realloc\_dbg](../../c-runtime-library/reference/realloc-dbg.md)に解決されます。  ヒープのデバッグ中にどのように管理されるかを詳細については、「[CRT のデバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  
  
 `realloc` は グローバル変数を変更せずに関数が保証され、返されたポインターが、エイリアス化されたことを意味するマークされた `__declspec(noalias)` と `__declspec(restrict)`です。  詳細については、「[noalias](../../cpp/noalias.md) と [restrict](../../cpp/restrict.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`realloc`|\<stdlib.h\> および \<malloc.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_realloc.c  
// This program allocates a block of memory for  
// buffer and then uses _msize to display the size of that  
// block. Next, it uses realloc to expand the amount of  
// memory used by buffer and then calls _msize again to  
// display the new amount of memory allocated to buffer.  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   long *buffer, *oldbuffer;  
   size_t size;  
  
   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )  
      exit( 1 );  
  
   size = _msize( buffer );  
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );  
  
   // Reallocate and show new size:  
   oldbuffer = buffer;     // save pointer in case realloc fails  
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))   
        ==  NULL )  
   {  
      free( oldbuffer );  // free original block  
      exit( 1 );  
   }  
   size = _msize( buffer );  
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",   
            size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
  **1000 の malloc 後のブロックのサイズは型: 4000**  
**1000 の realloc の後のブロックのサイズは、型: 8000**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)