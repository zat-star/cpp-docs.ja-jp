---
title: _realloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _realloc_dbg
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
- _realloc_dbg
- realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
caps.latest.revision: 15
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
ms.openlocfilehash: 0104c900c01ddf28a0e60a2263cd8d370fdfa8d8
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="reallocdbg"></a>_realloc_dbg
ブロックの移動やサイズ変更によって、ヒープ内の指定されたメモリのブロックを再割り当てします (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
void *_realloc_dbg(  
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
 再割り当てされるブロックのために要求するサイズ (バイト)。  
  
 `blockType`  
 再割り当てされるブロックのために要求する種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 `filename`  
 `realloc` 操作を要求したソース ファイル名へのポインター、または NULL。  
  
 `linenumber`  
 `realloc` 操作が要求されたソース ファイル内の行番号または NULL。  
  
 `filename` パラメーターと `linenumber` パラメーターを使用できるのは、`_realloc_dbg` が明示的に呼び出された場合、または [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) プリプロセッサ定数が定義されている場合だけです。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、この関数は再割り当てされたメモリ ブロックのユーザー部分へのポインターを返すか、新しいハンドラー関数を呼び出すか、NULL を返します。 戻る動作の詳細については、後の「解説」のセクションを参照してください。 新しいハンドラー関数がどのように使用されるかの詳細については、[realloc](../../c-runtime-library/reference/realloc.md) 関数を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_realloc_dbg` は、[realloc](../../c-runtime-library/reference/realloc.md) 関数のデバッグ バージョンです。 [_DEBUG](../../c-runtime-library/debug.md) が定義されない場合、`_realloc_dbg` への各呼び出しは `realloc` への呼び出しになります。 `realloc` と `_realloc_dbg` はベース ヒープ内にメモリ ブロックを再割り当てしますが、`_realloc_dbg` はいくつかのデバッグ機能を提供しています。たとえば、リークをテストするための、ブロックのユーザー部分の両側のバッファー、特定の割り当ての種類を追跡するためのブロック型パラメーター、割り当て要求の起点を特定するための `filename`/`linenumber` 情報などです。  
  
 `_realloc_dbg` は、要求された `newSize` よりも少し多い領域を使用して指定されたメモリ ブロックを再割り当てします。 `newSize` は、最初に割り当てられたメモリ ブロックのサイズより大きくなったり小さくなったりする場合があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 再割り当てによって、元のメモリ ブロックがヒープ内の別の位置に移動されたり、メモリ ブロックのサイズが変わったりする場合があります。 メモリ ブロックが移動される場合、元のブロックの内容は上書きされます。  
  
 メモリ割り当てが失敗するか、必要なメモリの量 (前に説明したオーバーヘッドを含む) が `_realloc_dbg` を超えると、`errno` は `ENOMEM` を `_HEAP_MAXREQ` に設定します。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_realloc_dbg`|\<crtdbg.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
 「[_msize_dbg](../../c-runtime-library/reference/msize-dbg.md)」のトピックの例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)
