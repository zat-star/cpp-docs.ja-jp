---
title: _aligned_offset_malloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
caps.latest.revision: 8
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
ms.openlocfilehash: fb6714506013bcaf9e4d5f6064d7bb98f8e56562
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg
指定された配置境界にメモリを割り当てます (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
void * _aligned_offset_malloc_dbg(  
   size_t size,   
   size_t alignment,   
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `size`  
 要求されたメモリ割り当てのサイズ。  
  
 [入力] `alignment`  
 アラインメント値。2 の整数乗である必要があります。  
  
 [入力] `offset`  
 アラインメントを強制するためのメモリ割り当てへのオフセット。  
  
 [入力] `filename`  
 割り当て操作を要求したソース ファイル名へのポインターまたは NULL。  
  
 [入力] `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または NULL。  
  
## <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックへのポインター。操作が失敗した場合は `NULL`。  
  
## <a name="remarks"></a>コメント  
 `_aligned_offset_malloc_dbg` は、[_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) 関数のデバッグ バージョンです。 [_DEBUG](../../c-runtime-library/debug.md) が定義されない場合、`_aligned_offset_malloc_dbg` への各呼び出しは `_aligned_offset_malloc` への呼び出しになります。 `_aligned_offset_malloc` と `_aligned_offset_malloc_dbg` はベース ヒープ内にメモリ ブロックを割り当てますが、`_aligned_offset_malloc_dbg` はいくつかのデバッグ機能を提供します。たとえば、リークをテストするための、ブロックのユーザー部分の両側のバッファー、特定の割り当ての種類を追跡するためのブロック型パラメーター、割り当て要求の起点を特定するための `filename`/`linenumber` 情報などです。  
  
 `_aligned_offset_malloc_dbg` は、要求された `size` よりも少し多い領域を使用してメモリ ブロックを割り当てます。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。  
  
 `_aligned_offset_malloc_dbg` は、入れ子になった要素に対するアラインメントが必要な状況で便利です。たとえば、入れ子になったクラスに対するアラインメントが必要になった場合などです。  
  
 `_aligned_offset_malloc_dbg` は `malloc` を基盤にしています。詳細については、「[malloc](../../c-runtime-library/reference/malloc.md)」を参照してください。  
  
 この関数は、メモリ割り当てが失敗するか、要求されたサイズが `errno` より大きかった場合に、`ENOMEM` を `_HEAP_MAXREQ` に設定します。 `errno` に関する詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。 また、`_aligned_offset_malloc` はそのパラメーターを検証します。 `alignment` が 2 の累乗でないか、`offset` が `size` 以上で 0 以外である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_aligned_offset_malloc_dbg`|\<crtdbg.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)
