---
title: rand | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- rand
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
- rand
dev_langs:
- C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fecd9079de1ae846d83847eb299890d62c29d17
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="rand"></a>rand

よく知られていると完全に再現可能なアルゴリズムを使用して擬似乱数を生成します。 この関数のプログラムでより安全なバージョンは使用できません。参照してください[rand_s](../../c-runtime-library/reference/rand-s.md)です。 によって生成された番号`rand`暗号的に安全ではありません。 乱数生成のより安全な暗号を使用して`rand_s`で C++ 標準ライブラリで宣言された関数または[\<ランダム >](../../standard-library/random.md)です。

## <a name="syntax"></a>構文

```C
int rand( void );
```

## <a name="return-value"></a>戻り値

`rand` は、上述のように疑似乱数を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>コメント

`rand` 関数は、0 から `RAND_MAX` (32767) までの範囲の整数の擬似乱数を返します。 `rand` を呼び出す前に、[srand](../../c-runtime-library/reference/srand.md) を使用して擬似乱数ジェネレーターにシードを設定してください。

`rand`関数は、よく知られているシーケンスを生成し、暗号化機能として使用するためには不適切なです。 乱数生成のより安全な暗号を使用して`rand_s`で C++ 標準ライブラリで宣言された関数または[\<ランダム >](../../standard-library/random.md)です。 `rand()` の不具合やこれらの不具合に対する `<random>` の対応の詳細については、[このビデオ](http://go.microsoft.com/fwlink/?LinkId=397615)をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`rand`|\<stdlib.h>|

互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。

## <a name="example"></a>例

```C
// crt_rand.c
// This program seeds the random-number generator
// with the time, then exercises the rand function.
//

#include <stdlib.h>
#include <stdio.h>
#include <time.h>

void SimpleRandDemo( int n )
{
   // Print n random numbers.
   int i;
   for( i = 0; i < n; i++ )
      printf( "  %6d\n", rand() );
}

void RangedRandDemo( int range_min, int range_max, int n )
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   int i;
   for ( i = 0; i < n; i++ )
   {
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min;
      printf( "  %6d\n", u);
   }
}

int main( void )
{
   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   SimpleRandDemo( 10 );
   printf("\n");
   RangedRandDemo( -100, 100, 10 );
}
```

```Output
22036
18330
11651
27464
18093
 3284
11785
14686
11447
11285

   74
   48
   27
   65
   96
   64
   -5
  -42
  -55
   66
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)  
[srand](../../c-runtime-library/reference/srand.md)  
[rand_s](../../c-runtime-library/reference/rand-s.md)  