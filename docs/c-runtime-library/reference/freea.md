---
title: _freea | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _freea
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
- freea
- _freea
dev_langs:
- C++
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
caps.latest.revision: 18
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
ms.openlocfilehash: bd53960a97cc6647008b683e354df664941428e9
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="freea"></a>_freea
メモリ ブロックを割り当て解除または解放します。  
  
## <a name="syntax"></a>構文  
  
```  
void _freea(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `memblock`  
 以前割り当てられ、解放されるメモリ ブロック。  
  
## <a name="return-value"></a>戻り値  
 なし。  
  
## <a name="remarks"></a>コメント  
 `_freea` 関数は、以前に [_malloca](../../c-runtime-library/reference/malloca.md) の呼び出しによって割り当てられたメモリ ブロック (`memblock`) を割り当て解除します。 `_freea` は、ヒープまたはスタック上でメモリが割り当てられているかどうかを確認します。 スタック上で割り当てられている場合、`_freea` は何も行いません。 ヒープ上で割り当てられている場合、解放されるバイト数は、ブロックが割り当てられたときに要求されたバイト数と同じです。 `memblock` が `NULL` である場合、ポインターは無視され、`_freea` が直ちに返されます。 無効なポインター (`_malloca` によって割り当てられていないメモリ ブロックへのポインター) を解放しようとすると、以降の割り当て要求に影響を与え、エラーが発生する可能性があります。  
  
 `_freea`呼び出し`free`ヒープにメモリが割り当てられていることを検出した場合に内部的にします。 メモリが、ヒープまたはスタックのどちらにあるかは、割り当てられたメモリの直前のアドレスにメモリ内で配置されたマーカーによって決まります。  
  
 メモリの解放でエラーが発生すると、エラーの性質に関するオペレーティング システムからの情報が `errno` に設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 メモリ ブロックを解放すると、[_heapmin](../../c-runtime-library/reference/heapmin.md) が、未使用の領域を結合して、それらをオペレーティング システムに戻すことで、ヒープ上の空きメモリの量を最小限に抑えます。 オペレーティング システムにリリースされない解放されたメモリは、空きプールに復元され、再度割り当てに使用できます。  
  
 `_freea` に対する呼び出しは、`_malloca` に対するすべての呼び出しを伴う必要があります。 同じメモリ上で `_freea` を 2 回呼び出した場合もエラーになります。 特に、C ランタイム ライブラリのデバッグ バージョン (特に `_CRTDBG_MAP_ALLOC` を定義することで有効になった [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md) 機能) とアプリケーションがリンクされている場合、見つからないまたは重複した `_freea` の呼び出しを簡単に見つけることができます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
 `_freea` は `__declspec(noalias)` としてマークされます。これは、関数がグローバル変数を変更しないことを保証します。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_freea`|\<stdlib.h> と \<malloc.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 「[_malloca](../../c-runtime-library/reference/malloca.md)」の例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)
