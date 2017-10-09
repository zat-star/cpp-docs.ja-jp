---
title: _aligned_offset_malloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7322f5a3fbf7bf3d9352181a68db17fad4bc9fcb
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc
指定された配置の境界にメモリを割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
void * _aligned_offset_malloc(  
   size_t size,   
   size_t alignment,   
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `size`  
 要求されたメモリ割り当てのサイズ。  
  
 [入力] `alignment`  
 アラインメント値。2 の整数乗である必要があります。  
  
 [入力] `offset`  
 アラインメントを強制するためのメモリ割り当てへのオフセット。  
  
## <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックへのポインター。操作が失敗した場合は `NULL`。  
  
## <a name="remarks"></a>コメント  
 `_aligned_offset_malloc` は、入れ子になった要素に対するアラインメントが必要な状況で便利です。たとえば、入れ子になったクラスに対するアラインメントが必要になった場合などです。  
  
 `_aligned_offset_malloc` は `malloc` を基盤にしています。詳細については、「[malloc](../../c-runtime-library/reference/malloc.md)」を参照してください。  
  
 `_aligned_offset_malloc` が `__declspec(noalias)` と `__declspec(restrict)` でマークされている場合、この関数がグローバル変数を変更せず、返されるポインターがエイリアス化されない保証があることを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。  
  
 この関数は、メモリ割り当てが失敗するか、要求されたサイズが `errno` より大きかった場合に、`ENOMEM` を `_HEAP_MAXREQ` に設定します。 `errno` に関する詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。 また、`_aligned_offset_malloc` はそのパラメーターを検証します。 `alignment` が 2 の累乗でないか、`offset` が `size` 以上で 0 以外である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_aligned_offset_malloc`|\<malloc.h>|  
  
## <a name="example"></a>例  
 詳細については、「[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [データの整列](../../c-runtime-library/data-alignment.md)
