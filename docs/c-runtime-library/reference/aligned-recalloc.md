---
title: _aligned_recalloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_recalloc
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
- aligned_recalloc
- _aligned_recalloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_recalloc function
- _aligned_recalloc function
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
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
ms.openlocfilehash: 9fbaae148ea373287991ebccbf53a5a859475d0c
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="alignedrecalloc"></a>_aligned_recalloc
[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリ ブロックのサイズを変更し、メモリを 0 に初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
void * _aligned_recalloc(  
   void *memblock,   
   size_t num,  
   size_t size,   
   size_t alignment  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `memblock`  
 現在のメモリ ブロック ポインター。  
  
 [入力] `num`  
 要素の数。  
  
 [入力] `size`  
 各要素のサイズ (バイト単位)。  
  
 [入力] `alignment`  
 配置の値。2 の累乗の整数である必要があります。  
  
## <a name="return-value"></a>戻り値  
 `_aligned_recalloc` は、再割り当てされた (移動された可能性もある) メモリ ブロックへの void ポインターを返します。 サイズが 0 でバッファー引数が `NULL` ではない場合、または特定のサイズにブロックを拡張するのに十分なメモリを使用できない場合、戻り値は `NULL` です。 最初の場合には、元のブロックは解放されます。 2 番目の場合には、元のブロックは変更されません。 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。  
  
 メモリを再割り当てしてブロックのアラインメントを変更すると、エラーになります。  
  
## <a name="remarks"></a>コメント  
 `_aligned_recalloc` は `malloc` に基づきます。 `_aligned_offset_malloc` の使用方法の詳細については、「[malloc](../../c-runtime-library/reference/malloc.md)」を参照してください。  
  
 この関数は、メモリ割り当てが失敗するか、要求されたサイズが `errno` より大きかった場合に、`ENOMEM` を `_HEAP_MAXREQ` に設定します。 `errno` に関する詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。 また、`_aligned_recalloc` はそのパラメーターを検証します。 `alignment` が 2 の累乗でない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数によって無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_aligned_recalloc`|\<malloc.h>|  
  
## <a name="see-also"></a>関連項目  
 [データの整列](../../c-runtime-library/data-alignment.md)   
 [_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)
