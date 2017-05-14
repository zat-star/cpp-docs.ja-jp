---
title: "_STATIC_ASSERT マクロ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
- _STATIC_ASSERT
dev_langs:
- C++
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
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
ms.openlocfilehash: 265796cdebbed1c0a067c44bbe6b71077be44a2b
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="staticassert-macro"></a>_STATIC_ASSERT マクロ
コンパイル時に式を評価し、結果が `FALSE` の場合にエラーを生成します。  
  
## <a name="syntax"></a>構文  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 ゼロ以外 (`TRUE`) またはゼロ (`FALSE`) に評価される式 (ポインターを含む)。  
  
## <a name="remarks"></a>コメント  
 このマクロは、[_ASSERT マクロと _ASSERTE マクロ](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)に似ていますが、`booleanExpression` は実行時ではなく、コンパイル時に評価される点が異なります。 `booleanExpression` が `FALSE` (0) に評価される場合、[コンパイラ エラー C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) が生成されます。  
  
## <a name="example"></a>例  
 この例では、`int` の `sizeof` が 2 バイト以上かどうか、および `long`の `sizeof` が 1 バイトかどうかを確認します。 `long` が 1 バイトを超えているため、プログラムはコンパイルされず、[コンパイラ エラー C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) が生成されます。  
  
```  
// crt__static_assert.c  
  
#include <crtdbg.h>  
#include <stdio.h>  
  
_STATIC_ASSERT(sizeof(int) >= 2);  
_STATIC_ASSERT(sizeof(long) == 1);  // C2466  
  
int main()  
{  
    printf("I am sure that sizeof(int) will be >= 2: %d\n",  
        sizeof(int));  
    printf("I am not so sure that sizeof(long) == 1: %d\n",  
        sizeof(long));  
}  
```  
  
## <a name="requirements"></a>要件  
  
|マクロ|必須ヘッダー|  
|-----------|---------------------|  
|`_STATIC_ASSERT`|\<crtdbg.h>|  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_ASSERT、_ASSERTE、_ASSERT_EXPR マクロ](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)
