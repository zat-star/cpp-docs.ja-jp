---
title: realloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- realloc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _brealloc
- _nrealloc
- realloc
- _frealloc
dev_langs:
- C++
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: a3612dfc9906b23bd3581729fd1de53212fb4b1a
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="realloc"></a>realloc
メモリ ブロックを再割り当てします。  
  
## <a name="syntax"></a>構文  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `memblock`  
 以前に割り当てられたメモリ ブロックへのポインター。  
  
 `size`  
 新しいサイズ (バイト単位)。  
  
## <a name="return-value"></a>戻り値  
 `realloc` は、再割り当てされた (移動された可能性もある) メモリ ブロックへの `void` ポインターを返します。  
  
 指定されたサイズにブロックを拡張するための十分な使用可能なメモリがない場合、元のブロックは変更されず、`NULL` が返されます。  
  
 `size` がゼロの場合は、`memblock` によってポイントされているブロックが解放されます。戻り値は `NULL` で、`memblock` は解放されたブロックをポイントしたままです。  
  
 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 `void` 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。  
  
## <a name="remarks"></a>コメント  
 `realloc` 関数は、割り当てられたメモリ ブロックのサイズを変更します。 `memblock` 引数はメモリ ブロックの先頭をポイントします。 `memblock` が `NULL` の場合、`realloc` は `malloc` と同様に動作し、`size` バイトの新しいブロックを割り当てます。 `memblock` が `NULL` でない場合は、`calloc`、`malloc`、または `realloc` の前回の呼び出しによって返されたポインターになると考えられます。  
  
 `size` 引数は、ブロックの新しいサイズをバイト単位で指定します。 新旧のサイズのうち、小さい方のブロックの内容は変更されませんが、新しいブロックの場所は異なる場合があります。 新しいブロックは新しいメモリ位置に配置される可能性があるため、`realloc` によって返されるポインターは、`memblock` 引数を通じて渡されたポインターと一致しないことがあります。 `realloc` では、バッファーが拡張される場合、新しく割り当てられたメモリをゼロで初期化しません。  
  
 メモリの割り当てに失敗した場合、または要求されたメモリ量が `_HEAP_MAXREQ` を超える場合、`realloc` は `errno` を `ENOMEM` に設定します。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 `realloc` は、C++ の [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 関数を使用して新しいハンドラー モードを設定するために `malloc` を呼び出します。 新しいハンドラー モードは、エラーが発生したときに、`malloc` が [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。 既定では、`malloc` は、メモリの割り当てエラーの際に新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドすると、`realloc` がメモリの割り当てに失敗したときに、`malloc` 演算子が同じ理由で失敗したときと同じ方法で、`new` によって新しいハンドラー ルーチンを呼び出すことができます。 既定の動作をオーバーライドするには、次の関数を呼び出します。  
  
```  
_set_new_mode(1)  
```  
  
 この呼び出しはプログラムの最初の方で指定するか、NEWMODE.OBJ にリンクします (「[リンク オプション](../../c-runtime-library/link-options.md)」を参照してください)。  
  
 アプリケーションが C のランタイム ライブラリのデバッグ バージョンにリンクされている場合、`realloc` は [_realloc_dbg](../../c-runtime-library/reference/realloc-dbg.md) として解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
 `realloc` は `__declspec(noalias)` と `__declspec(restrict)` でマークされています。これは、この関数がグローバル変数を変更せず、返されるポインターがエイリアス化されない保証があることを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`realloc`|\<stdlib.h> と \<malloc.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
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
  
```Output  
Size of block after malloc of 1000 longs: 4000  
Size of block after realloc of 1000 more longs: 8000  
```  
  
## <a name="see-also"></a>関連項目  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)
