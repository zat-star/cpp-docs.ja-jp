---
title: _aligned_msize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _aligned_msize
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
- _aligned_msize
- aligned_msize
dev_langs:
- C++
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e42427fd5c1c879b82dae4f8580627fbfbe67820
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="alignedmsize"></a>_aligned_msize
ヒープで割り当てられたメモリ ブロックのサイズを返します。  
  
## <a name="syntax"></a>構文  
  
```  
size_t _msize(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `memblock`  
 メモリ ブロックへのポインター。  
  
 [入力] `alignment`  
 アラインメント値。2 の整数乗である必要があります。  
  
 [入力] `offset`  
 アラインメントを強制するためのメモリ割り当てへのオフセット。  
  
## <a name="return-value"></a>戻り値  
 符号なし整数としてサイズ (バイト数) を返します。  
  
## <a name="remarks"></a>コメント  
 `_aligned_msize` 関数は、[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [_aligned_realloc](../../c-runtime-library/reference/aligned-realloc.md) への呼び出しで割り当てられたメモリ ブロックのサイズ (バイト数) を返します。 `alignment` と `offset` の値は、ブロックを割り当てた関数に渡される値と同じである必要があります。  
  
 アプリケーションが C のランタイム ライブラリのデバッグ バージョンにリンクされている場合、`_aligned_msize` は [_aligned_msize_dbg](../../c-runtime-library/reference/aligned-msize-dbg.md) として解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
 この関数は、そのパラメーターを検証します。 `memblock` が null ポインターであるか `alignment` が 2 の累乗でない場合、`_msize` は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 エラーが処理されると、`errno` が `EINVAL` に設定され、-1 が返されます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)