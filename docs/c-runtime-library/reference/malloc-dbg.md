---
title: _malloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _malloc_dbg
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
- malloc_dbg
- _malloc_dbg
dev_langs: C++
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fc67af9abb5602cca81eefa6aaeb131423057678
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mallocdbg"></a>_malloc_dbg
デバッグ ヘッダーと上書きバッファー用の追加の領域を持つメモリ ブロックをヒープに割り当てます (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
void *_malloc_dbg(  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `size`  
 要求するメモリ ブロックのサイズ (バイト単位)。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインターまたは NULL。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または NULL。  
  
 `filename` パラメーターと `linenumber` パラメーターを使用できるのは、`_malloc_dbg` が明示的に呼び出された場合、または [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) プリプロセッサ定数が定義されている場合だけです。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、この関数は割り当てられたメモリ ブロックのユーザー部分へのポインターを返すか、新しいハンドラー関数を呼び出すか、NULL を返します。 戻る動作の詳細については、後の「解説」のセクションを参照してください。 新しいハンドラー関数がどのように使用されるかの詳細については、[malloc](../../c-runtime-library/reference/malloc.md) 関数を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_malloc_dbg` は、[malloc](../../c-runtime-library/reference/malloc.md) 関数のデバッグ バージョンです。 [_DEBUG](../../c-runtime-library/debug.md) が定義されない場合、`_malloc_dbg` への各呼び出しは `malloc` への呼び出しになります。 `malloc` と `_malloc_dbg` はベース ヒープ内にメモリ ブロックを割り当てますが、`_malloc_dbg` はいくつかのデバッグ機能を提供します。たとえば、リークをテストするための、ブロックのユーザー部分の両側のバッファー、特定の割り当ての種類を追跡するためのブロック型パラメーター、割り当て要求の起点を特定するための `filename`/`linenumber` 情報などです。  
  
 `_malloc_dbg` は、要求された `size` よりも少し多い領域を使用してメモリ ブロックを割り当てます。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。  
  
 メモリ割り当てが失敗するか、必要なメモリの量 (前に説明したオーバーヘッドを含む) が `_malloc_dbg` を超えると、`errno` は `ENOMEM` を `_HEAP_MAXREQ` に設定します。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_malloc_dbg`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
 `_malloc_dbg` の使用例については、「[crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_calloc_dbg](../../c-runtime-library/reference/calloc-dbg.md)   
 [_calloc_dbg](../../c-runtime-library/reference/calloc-dbg.md)