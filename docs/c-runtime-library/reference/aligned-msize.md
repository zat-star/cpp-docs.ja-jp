---
title: _aligned_msize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: ac7ad08c7040ca317ef9e9a95acab6a8df3a7eed
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

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
  
 アプリケーションが C のランタイム ライブラリのデバッグ バージョンにリンクされている場合、`_aligned_msize` は [_aligned_msize_dbg](../../c-runtime-library/reference/aligned-msize-dbg.md) として解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
 この関数は、そのパラメーターを検証します。 `memblock` が null ポインターであるか `alignment` が 2 の累乗でない場合、`_msize` は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 エラーが処理されると、`errno` が `EINVAL` に設定され、-1 が返されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>関連項目  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)
