---
title: malloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- malloc
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
- malloc
dev_langs:
- C++
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 65b70ba6be4837a36d5987e60b1d7229134ceb99
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="malloc"></a>malloc
メモリ ブロックを割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
void *malloc(  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `size`  
 割り当てるバイト数。  
  
## <a name="return-value"></a>戻り値  
 `malloc` は、割り当てられた領域に void ポインターを返すか、メモリが不足している場合、`NULL` を返します。 `void` 以外の型へのポインターを返すには、戻り値の型キャストを使用します。 戻り値が指すストレージ領域は、オブジェクトのアラインメント要件が基本的なアラインメントの要件以下である限り、どの型のオブジェクトを格納する場合でも、適切なアラインメントが保証されます  (Visual C++ の基本的なアラインメントは、`double`、つまり 8 バイトに対して必要なアラインメントです。 64 ビット プラットフォームを対象としたコードでは 16 バイトです)。アラインメント要件が基本的なアラインメントの要件を超える場合は、[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) を使用してオブジェクトのストレージを割り当てます。たとえば、SSE 型の [__m128](../../cpp/m128.md) や `__m256`、また `__declspec(align( n ))` で `n` に 8 を超える数値を設定して宣言した型などです。 `size` が 0 の場合、`malloc` 関数はヒープに長さが 0 のアイテムを割り当て、そのアイテムへの有効なポインターを返します。 要求されたメモリ量が小さい場合でも、`malloc` からの戻り値を必ずチェックしてください。  
  
## <a name="remarks"></a>コメント  
 `malloc` 関数は、少なくとも `size` バイトのメモリ ブロックを割り当てます。 アラインメントと保守情報に領域が必要なため、ブロックのサイズが `size` バイトを超えることがあります。  
  
 `malloc` を実行したときに、メモリの割り当てに失敗した場合、または要求されたメモリ量が `errno` を超える場合は、`ENOMEM` が `_HEAP_MAXREQ` に設定されます。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 スタートアップ コードは `malloc` を使用して、変数 `_environ`、`envp`、および `argv` にストレージを割り当てます。 次の関数やこれらに対応するワイド文字関数も、`malloc` を呼び出します。  
  
|||||  
|-|-|-|-|  
|[calloc](../../c-runtime-library/reference/calloc.md)|[fscanf](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](../../c-runtime-library/reference/getw.md)|[setvbuf](../../c-runtime-library/reference/setvbuf.md)|  
|[_exec 関数](../../c-runtime-library/exec-wexec-functions.md)|[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)|[_popen](../../c-runtime-library/reference/popen-wpopen.md)|[_spawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)|  
|[fgetc](../../c-runtime-library/reference/fgetc-fgetwc.md)|[fsetpos](../../c-runtime-library/reference/fsetpos.md)|[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_strdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)|  
|[_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md)|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[putc](../../c-runtime-library/reference/putc-putwc.md)|[system](../../c-runtime-library/reference/system-wsystem.md)|  
|[fgets](../../c-runtime-library/reference/fgets-fgetws.md)|[fwrite](../../c-runtime-library/reference/fwrite.md)|[putchar](../../c-runtime-library/reference/putc-putwc.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](../../c-runtime-library/reference/getc-getwc.md)|[_putenv](../../c-runtime-library/reference/putenv-wputenv.md)|[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)|  
|[fputc](../../c-runtime-library/reference/fputc-fputwc.md)|[getchar](../../c-runtime-library/reference/getc-getwc.md)|[puts](../../c-runtime-library/reference/puts-putws.md)|[vfprintf](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[_fputchar](../../c-runtime-library/reference/fputc-fputwc.md)|[_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[_putw](../../c-runtime-library/reference/putw.md)|[vprintf](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|  
|[fputs](../../c-runtime-library/reference/fputs-fputws.md)|[_getdcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)||  
|[fread](../../c-runtime-library/reference/fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)||  
  
 C++ の [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 関数は `malloc` の新しいハンドラー モードを設定します。 新しいハンドラー モードは、エラーが発生したときに、`malloc` が [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。 既定では、`malloc` は、メモリの割り当てエラーの際に新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドすると、`malloc` がメモリの割り当てに失敗したときに、`malloc` 演算子が同じ理由で失敗したときと同じ方法で、`new` によって新しいハンドラー ルーチンを呼び出すことができます。 既定値を上書きするには、呼び出す`_set_new_mode(1)`早い段階で、プログラム、または NEWMODE とリンクします。OBJ (を参照してください[リンク オプション](../../c-runtime-library/link-options.md))。  
  
 アプリケーションが C のランタイム ライブラリのデバッグ バージョンにリンクされている場合、`malloc` は [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md) として解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
 `malloc` が `__declspec(noalias)` と `__declspec(restrict)` でマークされている場合、この関数がグローバル変数を変更せず、返されるポインターがエイリアス化されない保証があることを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`malloc`|\<stdlib.h> と \<malloc.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```C  
// crt_malloc.c  
// This program allocates memory with  
// malloc, then frees the memory with free.  
  
#include <stdlib.h>   // For _MAX_PATH definition  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   char *string;  
  
   // Allocate space for a path name  
   string = malloc( _MAX_PATH );  
  
   // In a C++ file, explicitly cast malloc's return.  For example,   
   // string = (char *)malloc( _MAX_PATH );  
  
   if( string == NULL )  
      printf( "Insufficient memory available\n" );  
   else  
   {  
      printf( "Memory space allocated for path name\n" );  
      free( string );  
      printf( "Memory freed\n" );  
   }  
}  
```  
  
```Output  
Memory space allocated for path name  
Memory freed  
```  
  
## <a name="see-also"></a>参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)
