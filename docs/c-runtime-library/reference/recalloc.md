---
title: _recalloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _recalloc
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
- _recalloc
- recalloc
dev_langs: C++
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 007f174b3cbdb7e8ca53af19b6f9764200ff690a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="recalloc"></a>_recalloc
`realloc` と `calloc` の組み合わせです。 メモリ内の配列を再割り当てし、その要素を 0 に初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `memblock`  
 以前に割り当てられていたメモリ ブロックへのポインター。  
  
 `num`  
 要素の数。  
  
 `size`  
 各要素の長さ (バイト単位)。  
  
## <a name="return-value"></a>戻り値  
 `_recalloc` は、再割り当てされた (移動された可能性もある) メモリ ブロックへの `void` ポインターを返します。  
  
 指定されたサイズにブロックを拡張するための十分な使用可能なメモリがない場合、元のブロックは変更されず、`NULL` が返されます。  
  
 要求されたサイズがゼロの場合は、`memblock` によってポイントされているブロックが解放されます。戻り値は `NULL` で、`memblock` は解放されたブロックをポイントしたままです。  
  
 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 `void` 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。  
  
## <a name="remarks"></a>コメント  
 `_recalloc` 関数は、割り当てられたメモリ ブロックのサイズを変更します。 `memblock` 引数はメモリ ブロックの先頭をポイントします。 場合`memblock`は`NULL`、`_recalloc`と同様に動作[calloc](../../c-runtime-library/reference/calloc.md)し、新しいブロックを割り当てます`num`  *  `size`バイトです。 各要素は 0 に初期化されます。 `memblock` が `NULL` でない場合は、`calloc`、[malloc](../../c-runtime-library/reference/malloc.md)、または [realloc](../../c-runtime-library/reference/realloc.md) の前回の呼び出しによって返されたポインターである必要があります。  
  
 新しいブロックは新しいメモリ位置に配置される可能性があるため、`_recalloc` によって返されるポインターは、`memblock` 引数を通じて渡されたポインターと一致しないことがあります。  
  
 メモリの割り当てに失敗した場合、または要求されたメモリ量が `_HEAP_MAXREQ` を超える場合、`_recalloc` は `errno` を `ENOMEM` に設定します。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 `recalloc` は、C++ の [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 関数を使用して新しいハンドラー モードを設定するために `realloc` を呼び出します。 新しいハンドラー モードは、エラーが発生したときに、`realloc` が [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。 既定では、`realloc` は、メモリの割り当てエラーの際に新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドすると、`_recalloc` がメモリの割り当てに失敗したときに、`realloc` 演算子が同じ理由で失敗したときと同じ方法で、`new` によって新しいハンドラー ルーチンを呼び出すことができます。 既定の動作をオーバーライドするには、次の関数を呼び出します。  
  
```  
_set_new_mode(1)  
```  
  
 この呼び出しはプログラムの最初の方で指定するか、NEWMODE.OBJ にリンクします。  
  
 C ランタイム ライブラリのデバッグ バージョンとリンクするアプリケーション`_recalloc`に解決される[_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md)です。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
 `_recalloc` は `__declspec(noalias)` と `__declspec(restrict)` でマークされています。これは、この関数がグローバル変数を変更せず、返されるポインターがエイリアス化されない保証があることを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_recalloc`|\<stdlib.h> と \<malloc.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [リンク オプション](../../c-runtime-library/link-options.md)