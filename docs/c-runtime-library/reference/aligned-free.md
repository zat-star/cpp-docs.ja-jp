---
title: _aligned_free | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_free
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
- aligned_free
- _aligned_free
dev_langs: C++
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d65782fe3d381cfc8916670b3e6db1bf378a6c5d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="alignedfree"></a>_aligned_free
[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリ ブロックを解放します。  
  
## <a name="syntax"></a>構文  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `memblock`  
 `_aligned_malloc` または `_aligned_offset_malloc` 関数に返されたメモリ ブロックへのポインター。  
  
## <a name="remarks"></a>コメント  
 `_aligned_free` は `__declspec(noalias)` としてマークされます。これは、関数がグローバル変数を変更しないことを保証します。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。  
  
 この関数は、他の _aligned CRT 関数とは異なり、パラメーターを検証しません。 `memblock` が `NULL` ポインターの場合、この関数は何のアクションも実行しません。 この関数は `errno` を変更せず、無効なパラメーター ハンドラーを呼び出しません。 以前にメモリのブロックを割り当てるために _aligned 関数を使用しなかったために関数でエラーが発生する場合、または何らかの予期しない災害によってメモリの不整合が発生する場合、関数は [_RPT、_RPTF、_RPTW、_RPTFW のマクロ](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)からデバッグ レポートを生成します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_aligned_free`|\<malloc.h>|  
  
## <a name="example"></a>例  
 詳細については、「[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [データの整列](../../c-runtime-library/data-alignment.md)