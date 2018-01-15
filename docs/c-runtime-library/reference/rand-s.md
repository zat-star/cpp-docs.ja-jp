---
title: rand_s | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: rand_s
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
f1_keywords: rand_s
dev_langs: C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d5fde51ee8fb65426166d9d5d2e7d6e5873dd6e8
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2018
---
# <a name="rands"></a>rand_s

疑似乱数を生成します。 これは、関数のバージョンがより安全な[rand](../../c-runtime-library/reference/rand.md)のセキュリティが強化された」の説明に従って[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)します。 

## <a name="syntax"></a>構文

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>パラメーター

*確率*  
生成された値を保持する整数へのポインター。

## <a name="return-value"></a>戻り値

正常に終了した場合は 0 を返し、それ以外の場合はエラー コードを返します。 場合は入力ポインター_確率_null ポインター」の説明に従って、関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。 その他の何らかの理由で失敗した場合 *_確率_は 0 に設定します。

## <a name="remarks"></a>コメント

`rand_s` 関数は、0 ～ `UINT_MAX` の範囲の整数の擬似乱数を入力ポインターに書き込みます。 `rand_s` 関数では、オペレーティング システムを使用して、暗号強度が高い乱数を生成します。 この関数は [srand](../../c-runtime-library/reference/srand.md) 関数の生成したシードを使用せず、また `rand` の使用するランダムな数値のシーケンスに影響を与えません。

`rand_s` 関数を宣言するには、インクルード ステートメントの前に定数 `_CRT_RAND_S` を定義する必要があります。たとえば次の例のようになります。

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

`rand_s` は [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694) API に依存しますが、この API は Windows XP 以降でのみ利用できます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`rand_s`|\<stdlib.h>|

詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
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

### <a name="sample-output"></a>出力例

```Output
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
[rand](../../c-runtime-library/reference/rand.md)  
[srand](../../c-runtime-library/reference/srand.md)  
