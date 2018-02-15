---
title: _aligned_msize_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0c26a876f6ef4f77d4f9c649a3993fe666cb6f3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg
ヒープで割り当てられたメモリ ブロックのサイズを返します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
size_t _aligned_msize_dbg(  
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
 `alignment` と `offset` の値は、ブロックを割り当てた関数に渡される値と同じである必要があります。  
  
 `_aligned_msize_dbg` は、[_aligned_msize](../../c-runtime-library/reference/aligned-msize.md) 関数のデバッグ バージョンです。 [_DEBUG](../../c-runtime-library/debug.md) が定義されない場合、`_aligned_msize_dbg` への各呼び出しは `_aligned_msize` への呼び出しになります。 `_aligned_msize` と `_aligned_msize_dbg` は、どちらもベース ヒープ内のメモリ ブロックのサイズを計算しますが、`_aligned_msize_dbg` はデバッグ機能を追加します。そのため、返されるサイズに、メモリ ブロックのユーザー部分の両側のバッファーが含められます。  
  
 この関数は、そのパラメーターを検証します。 `memblock` が null ポインターであるか `alignment` が 2 の累乗でない場合、`_msize` は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 エラーが処理されると、`errno` が `EINVAL` に設定され、-1 が返されます。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_aligned_msize_dbg`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)