---
title: "_expand_dbg | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _expand_dbg
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
apitype: DLLExport
f1_keywords:
- expand_dbg
- _expand_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41f3d59cec6ec4a064143e0211ebd956f30e16e5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="expanddbg"></a>_expand_dbg
ブロックの拡張や縮小によって、ヒープ内の指定されたメモリのブロックをサイズ変更します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
void *_expand_dbg(   
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `userData`  
 以前に割り当てられていたメモリ ブロックへのポインター。  
  
 `newSize`  
 ブロックのために要求する新しいサイズ (バイト単位)。  
  
 `blockType`  
 サイズ変更するブロックのために要求する型: `_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 `filename`  
 拡張操作を要求したソース ファイル名へのポインター、または `NULL`。  
  
 `linenumber`  
 拡張操作が要求されたソース ファイル内の行番号または `NULL`。  
  
 `filename` パラメーターと `linenumber` パラメーターを使用できるのは、`_expand_dbg` が明示的に呼び出された場合、または [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) プリプロセッサ定数が定義されている場合だけです。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`_expand_dbg` は、サイズ変更されたメモリ ブロックへのポインターを返します。 メモリが移動されないため、アドレスは userData と同じです。 エラーが発生したか、要求されたサイズまでブロックを拡張できない場合は、`NULL` が返されます。 エラーが発生すると、`errno` にはエラーの性質に関するオペレーティング システムからの情報が設定されます。 `errno` に関する詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_expand_dbg` 関数は、[_expand](../../c-runtime-library/reference/expand.md) 関数のデバッグ バージョンです。 [_DEBUG](../../c-runtime-library/debug.md) が定義されない場合、`_expand_dbg` への各呼び出しは `_expand` への呼び出しになります。 `_expand` と `_expand_dbg` はベース ヒープ内でメモリ ブロックをサイズ変更しますが、`_expand_dbg` はいくつかのデバッグ機能を提供します。たとえば、リークをテストするための、ブロックのユーザー部分の両側のバッファー、特定の割り当ての種類を追跡するためのブロック型パラメーター、割り当て要求の起点を特定するための `filename`/`linenumber` 情報などです。  
  
 `_expand_dbg` は、要求された `newSize` よりも少し多い領域を使用して指定されたメモリ ブロックをサイズ変更します。 `newSize` は、最初に割り当てられたメモリ ブロックのサイズより大きくなったり小さくなったりする場合があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 サイズ変更は、元のメモリ ブロックを拡張または縮小することで実現されます。 `_expand_dbg` は、メモリ ブロックを移動しません。一方、[_realloc_dbg](../../c-runtime-library/reference/realloc-dbg.md) 関数は、メモリ ブロックを移動します。  
  
 `newSize` が元のブロック サイズよりも大きい場合、メモリ ブロックは拡張されます。 拡張時に、要求されたサイズに合うようにメモリ ブロックを拡張できない場合は、`NULL` が返されます。 `newSize` が元のブロック サイズ未満の場合、メモリ ブロックは新しいサイズになるまで縮小されます。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。  
  
 この関数は、パラメーターを検証します。 `memblock` が null ポインターであるか、サイズが `_HEAP_MAXREQ` より大きい場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、関数から `NULL`が返されます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_expand_dbg`|\<crtdbg.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
  
```  
// crt_expand_dbg.c  
//  
// This program allocates a block of memory using _malloc_dbg  
// and then calls _msize_dbg to display the size of that block.  
// Next, it uses _expand_dbg to expand the amount of  
// memory used by the buffer and then calls _msize_dbg again to  
// display the new amount of memory allocated to the buffer.  
//  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   long *buffer;  
   size_t size;  
  
   // Call _malloc_dbg to include the filename and line number  
   // of our allocation request in the header  
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),  
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if( buffer == NULL )  
      exit( 1 );  
  
   // Get the size of the buffer by calling _msize_dbg  
   size = _msize_dbg( buffer, _NORMAL_BLOCK );  
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );  
  
   // Expand the buffer using _expand_dbg and show the new size  
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),  
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );  
  
   if( buffer == NULL )  
      exit( 1 );  
   size = _msize_dbg( buffer, _NORMAL_BLOCK );  
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",  
           size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
```Output  
Size of block after _malloc_dbg of 40 longs: 160  
Size of block after _expand_dbg of 1 more long: 164  
```  
  
## <a name="comment"></a>コメント  
 このプログラムの出力は、すべてのセクションを拡張するためのコンピューターの能力によって異なります。 すべてのセクションが展開される場合、出力は出力セクションに反映されます。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)