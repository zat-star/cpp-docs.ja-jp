---
title: free | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- free
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
- free
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: fa4dd487cc0a3f1f14f0bca955ca9059c4bbb964
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="free"></a>free
メモリ ブロックを割り当て解除または解放します。  
  
## <a name="syntax"></a>構文  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `memblock`  
 以前割り当てられ、解放されるメモリ ブロック。  
  
## <a name="remarks"></a>コメント  
 `free` 関数は、以前に `calloc`、`malloc`、または `realloc` の呼び出しによって割り当てられたメモリ ロック (`memblock`) を割り当て解除します。 解放されるバイト数は、ブロックが割り当てられたとき (または `realloc` の場合は再割り当てのとき) に要求されたバイト数と同じです。 `memblock` が `NULL` である場合、ポインターは無視され、`free` が直ちに返されます。 無効なポインター (`calloc`、`malloc`、または `realloc` によって割り当てられていないメモリ ブロックへのポインター) を解放しようとすると、以降の割り当て要求に影響を与え、エラーが発生する可能性があります。  
  
 メモリの解放でエラーが発生すると、エラーの性質に関するオペレーティング システムからの情報が `errno` に設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 メモリ ブロックを解放すると、[_heapmin](../../c-runtime-library/reference/heapmin.md) が、未使用の領域を結合して、それらをオペレーティング システムに戻すことで、ヒープ上の空きメモリの量を最小限に抑えます。 オペレーティング システムにリリースされない解放されたメモリは、空きプールに復元され、再度割り当てに使用できます。  
  
 アプリケーションが C のランタイム ライブラリのデバッグ バージョンにリンクされている場合、`free` は [_free_dbg](../../c-runtime-library/reference/free-dbg.md) として解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
 `free` は `__declspec(noalias)` としてマークされます。これは、関数がグローバル変数を変更しないことを保証します。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。  
  
 [_malloca](../../c-runtime-library/reference/malloca.md) を使用して割り当てられたメモリを解放するには、[_freea](../../c-runtime-library/reference/freea.md) を使用します。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`free`|\<stdlib.h> と \<malloc.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 「[malloc](../../c-runtime-library/reference/malloc.md)」の例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_freea](../../c-runtime-library/reference/freea.md)
