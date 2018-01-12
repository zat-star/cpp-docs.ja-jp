---
title: _query_new_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _query_new_mode
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
- query_new_mode
- _query_new_mode
dev_langs: C++
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 385d6edc77387b724c4e121a9fc01cee1a4d8905
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="querynewmode"></a>_query_new_mode
`malloc` に対して `_set_new_mode` によって設定された新しいハンドラー モードを示す整数を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## <a name="return-value"></a>戻り値  
 `malloc` に対して現在の新しいハンドラー モード、つまり 0 または 1 を返します。 戻り値 1 は、メモリの割り当てに失敗したときに、`malloc` が新しいハンドラー ルーチンを呼び出すことを指定し、戻り値 0 は呼び出さないことを指定します。  
  
## <a name="remarks"></a>コメント  
 C++ の `_query_new_mode` 関数は、[malloc](../../c-runtime-library/reference/malloc.md) に対して C++ の [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 関数によって設定された新しいハンドラー モードを示す整数を返します。 新しいハンドラー モードは、メモリの割り当てに失敗したときに、`malloc` が [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。 既定では、`malloc` は、エラーの際に新しいハンドラー ルーチンを呼び出しません。 `_set_new_mode` を使用してこの動作をオーバーライドすると、**new** 演算子がメモリの割り当てに失敗したときと同じ方法で、エラー発生時に `malloc` によって新しいハンドラー ルーチンを呼び出すことができます。 詳細については、C++ 言語リファレンスの「[new および delete 演算子](../../cpp/new-and-delete-operators.md)」の説明をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_query_new_mode`|\<new.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)