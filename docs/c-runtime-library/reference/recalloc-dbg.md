---
title: _recalloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _recalloc_dbg
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
- recalloc_dbg
- _recalloc_dbg
dev_langs: C++
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dfd6489945ee4eb5ede32f010d474a2cb428ff97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="recallocdbg"></a>_recalloc_dbg
配列を再割り当てし、その要素を 0 に初期化します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
void *_recalloc_dbg(   
   void *userData,  
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `userData`  
 以前に割り当てられていたメモリ ブロックへのポインター。  
  
 `num`  
 要求するメモリ ブロックの数。  
  
 `size`  
 要求する各メモリ ブロックのサイズ (バイト)。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインター、または `NULL`。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または `NULL`。  
  
 `filename` パラメーターと `linenumber` パラメーターを使用できるのは、`_recalloc_dbg` が明示的に呼び出された場合、または [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) プリプロセッサ定数が定義されている場合だけです。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、この関数は再割り当てされたメモリ ブロックのユーザー部分へのポインターを返すか、新しいハンドラー関数を呼び出すか、NULL を返します。 戻る動作の詳細については、後の「解説」のセクションを参照してください。 新しいハンドラー関数がどのように使用されるかの詳細については、[_recalloc](../../c-runtime-library/reference/recalloc.md) 関数を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_recalloc_dbg` は、[_recalloc](../../c-runtime-library/reference/recalloc.md) 関数のデバッグ バージョンです。 [_DEBUG](../../c-runtime-library/debug.md) が定義されない場合、`_recalloc_dbg` への各呼び出しは `_recalloc` への呼び出しになります。 `_recalloc` と `_recalloc_dbg` はベース ヒープ内にメモリ ブロックを再割り当てしますが、`_recalloc_dbg` はいくつかのデバッグ機能を提供しています。たとえば、リークをテストするための、ブロックのユーザー部分の両側のバッファー、特定の割り当ての種類を追跡するためのブロック型パラメーター、割り当て要求の起点を特定するための `filename`/`linenumber` 情報などです。  
  
 `_recalloc_dbg` は、要求されたサイズ (`num` * `size`) よりも少し多い領域を使用して指定されたメモリ ブロックを再割り当てします。要求されたサイズは、最初に割り当てられたメモリ ブロックのサイズより大きくなったり小さくなったりする場合があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 再割り当てによって、元のメモリ ブロックがヒープ内の別の位置に移動されたり、メモリ ブロックのサイズが変わったりする場合があります。 ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。  
  
 メモリ割り当てが失敗すると、`_recalloc_dbg` は `errno` を `ENOMEM` に設定します。必要なメモリの量 (前に説明したオーバーヘッドを含む) が `EINVAL` を超えると、`_HEAP_MAXREQ` が返されます。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_recalloc_dbg`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)