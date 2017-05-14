---
title: "_expand | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: b82bcf0de4f17a718389ef358a11a88e9bd999c1
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="expand"></a>_expand
メモリ ブロックのサイズを変更します。  
  
## <a name="syntax"></a>構文  
  
```  
void *_expand(   
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
 `_expand` は再割り当て済みのメモリ ブロックに void ポインターを返します。 `_expand` は `realloc` とは異なり、ブロックを移動してそのサイズを変更することはできません。 したがって、ブロックを拡張するのに十分なメモリが使用できるためブロックを移動する必要がない場合、`_expand` への `memblock` パラメーターは戻り値と同じになります。  
  
 `_expand` は、操作中にエラーが検出された場合、`NULL` を返します。 たとえば、`_expand` を使用してメモリ ブロックを縮小する場合、小さなブロック ヒープ内の破損や無効なブロック ポインターが検出されると、`NULL` が返されます。  
  
 移動せずに、指定したサイズにブロックを拡張するのに使用できる十分なメモリがない場合、この関数は `NULL` を返します。 `_expand` は、拡張されたブロックが要求されたサイズに届かなかった場合、そのブロックを返しません。 エラーが発生した場合、`errno` はエラーの性質を示します。 `errno` に関する詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 項目の新しいサイズを確認するには、`_msize` を使用します。 `void` 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。  
  
## <a name="remarks"></a>コメント  
 `_expand` 関数は、ヒープ内でブロックの場所を移動することなくブロックの拡張または縮小を試みることにより、以前に割り当てられたメモリ ブロックのサイズを変更します。 `memblock` パラメーターはブロックの先頭を指します。 `size` パラメーターはブロックの新しいサイズをバイト単位で指定します。 ブロックの内容は、新しいサイズと古いサイズのうち小さい方のサイズまでは変更されません。 `memblock` には、解放されたブロックを指定しないでください。  
  
> [!NOTE]
>  64 ビット プラットフォームでは、新しいサイズが現在のサイズよりも小さい場合、`_expand` はブロックを縮小しないことがあります。特に、ブロック サイズが 16K 未満で、そのブロックが Low Fragmentation Heap に割り当てられた場合、`_expand` はブロック サイズを変更せず、`memblock` を返します。  
  
 アプリケーションが C のランタイム ライブラリのデバッグ バージョンにリンクされている場合、`_expand` は [_expand_dbg](../../c-runtime-library/reference/expand-dbg.md) として解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
 この関数は、パラメーターを検証します。 また、`memblock` が null ポインターの場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、関数から `NULL`が返されます。 `size` が `_HEAP_MAXREQ` より大きい場合、`errno` は `ENOMEM` に設定され、関数は `NULL` を返します。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_expand`|\<malloc.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_expand.c  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char *bufchar;  
   printf( "Allocate a 512 element buffer\n" );  
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )  
      exit( 1 );  
   printf( "Allocated %d bytes at %Fp\n",   
         _msize( bufchar ), (void *)bufchar );  
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )  
      printf( "Can't expand" );  
   else  
      printf( "Expanded block to %d bytes at %Fp\n",   
            _msize( bufchar ), (void *)bufchar );  
   // Free memory   
   free( bufchar );  
   exit( 0 );  
}  
```  
  
```Output  
Allocate a 512 element buffer  
Allocated 512 bytes at 002C12BC  
Expanded block to 1024 bytes at 002C12BC  
```  
  
## <a name="see-also"></a>関連項目  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_msize](../../c-runtime-library/reference/msize.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)
