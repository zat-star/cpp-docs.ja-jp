---
title: rand_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- rand_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- rand_s
dev_langs:
- C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
ms.assetid: d6a0be60-997d-4904-8411-8aea6839cc94
caps.latest.revision: 24
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
ms.openlocfilehash: 5087948c5737f105e9bc694da1e866be659ff18f
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="rands"></a>rand_s
疑似乱数を生成します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [rand](../../c-runtime-library/reference/rand.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t rand_s(   unsigned int* randomValue);  
```  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は 0 を返し、それ以外の場合はエラー コードを返します。 入力ポインター `randomValue` が Null ポインターの場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。 その他の何らかの理由で関数が失敗した場合、*`randomValue` は 0 に設定されます。  
  
## <a name="remarks"></a>コメント  
 `rand_s` 関数は、0 ～ `UINT_MAX` の範囲の整数の擬似乱数を入力ポインターに書き込みます。 `rand_s` 関数では、オペレーティング システムを使用して、暗号強度が高い乱数を生成します。 この関数は [srand](../../c-runtime-library/reference/srand.md) 関数の生成したシードを使用せず、また `rand` の使用するランダムな数値のシーケンスに影響を与えません。  
  
 `rand_s` 関数を宣言するには、インクルード ステートメントの前に定数 `_CRT_RAND_S` を定義する必要があります。たとえば次の例のようになります。  
  
```  
#define _CRT_RAND_S  
#include <stdlib.h>  
```  
  
 `rand_s` は [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694) API に依存しますが、この API は Windows XP 以降でのみ利用できます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`rand_s`|\<stdlib.h>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_rand_s.c  
// This program illustrates how to generate random  
// integer or floating point numbers in a specified range.  
  
// Remembering to define _CRT_RAND_S prior  
// to inclusion statement.  
#define _CRT_RAND_S  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <limits.h>  
  
int main( void )  
{  
    int             i;  
    unsigned int    number;  
    double          max = 100.0;  
    errno_t         err;  
  
    // Display 10 random integers in the range [ 1,10 ].  
    for( i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %u\n", (unsigned int) ((double)number /  
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);  
    }  
  
    printf_s("\n");  
  
    // Display 10 random doubles in [0, max).  
    for (i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %g\n", (double) number /   
                          ((double) UINT_MAX + 1) * max );  
    }  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
10  
4  
5  
2  
8  
2  
5  
6  
1  
1  
  
32.6617  
29.4471  
11.5413  
6.41924  
20.711  
60.2878  
61.0094  
20.1222  
80.9192  
65.0712  
```  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)
