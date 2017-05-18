---
title: "difftime、_difftime32、_difftime64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _difftime32
- difftime
- _difftime64
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _difftime64
- difftime
- difftime64
- _difftime32
- difftime32
dev_langs:
- C++
helpviewer_keywords:
- _difftime32 function
- difftime function
- time, finding the difference
- difftime64 function
- _difftime64 function
- difftime32 function
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: f6ab058a86a5635aa341c964644a291f61ba170b
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="difftime-difftime32-difftime64"></a>difftime、_difftime32、_difftime64
2 つの時刻の差を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
double difftime(   
   time_t timer1,  
   time_t timer0   
);  
double _difftime32(   
   __time32_t timer1,  
   __time32_t timer0   
);  
double _difftime64(   
   __time64_t timer1,  
   __time64_t timer0   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `timer1`  
 終了時刻。  
  
 `timer0`  
 開始時刻。  
  
## <a name="return-value"></a>戻り値  
 `difftime` は、`timer0` から `timer1` までの経過時間を秒単位で返します。 返される値は、倍精度浮動小数点数です。 戻り値が 0 の場合は、エラーを示します。  
  
## <a name="remarks"></a>コメント  
 `difftime` 関数は、指定した 2 つの時刻値 `timer0` と `timer1` の差を計算します。  
  
 指定する時刻値は、`time_t` の範囲内に収まる必要があります。 `time_t` は 64 ビット値です。 したがって、範囲の終わりは、2038 年 1 月 18 日 23 時 59 分 59 秒 (UTC) から、3000 年 12 月 31 日 23 時 59 分 59 秒に拡張されました。 `time_t` の範囲の始まりは、1970 年 1 月 1 日午前 0 時で変わりません。  
  
 `difftime` はインライン関数であり、`_USE_32BIT_TIME_T` が定義されているかどうかに応じて `_difftime32` または `_difftime64` に評価されます。 _difftime32 と _difftime64 を直接使って、特定のサイズの時刻型の使用を強制できます。  
  
 これらの関数では、パラメーターの検証が行われます。 どちらかのパラメーターが 0 または負の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効パラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は 0 を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`difftime`|\<time.h>|  
|`_difftime32`|\<time.h>|  
|`_difftime64`|\<time.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```cpp  
// crt_difftime.c  
// This program calculates the amount of time  
// needed to do a floating-point multiply 100 million times.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
#include <float.h>  
  
double RangedRand( float range_min, float range_max)  
{  
   // Generate random numbers in the half-closed interval  
   // [range_min, range_max). In other words,  
   // range_min <= random number < range_max  
   return ((double)rand() / (RAND_MAX + 1) * (range_max - range_min)  
            + range_min);  
}  
  
int main( void )  
{  
   time_t   start, finish;  
   long     loop;  
   double   result, elapsed_time;  
   double   arNums[3];  
  
   // Seed the random-number generator with the current time so that  
   // the numbers will be different every time we run.  
   srand( (unsigned)time( NULL ) );  
  
   arNums[0] = RangedRand(1, FLT_MAX);  
   arNums[1] = RangedRand(1, FLT_MAX);  
   arNums[2] = RangedRand(1, FLT_MAX);  
   printf( "Using floating point numbers %.5e %.5e %.5e\n", arNums[0], arNums[1], arNums[2] );  
  
   printf( "Multiplying 2 numbers 100 million times...\n" );  
  
   time( &start );  
   for( loop = 0; loop < 100000000; loop++ )  
      result = arNums[loop%3] * arNums[(loop+1)%3];   
   time( &finish );  
  
   elapsed_time = difftime( finish, start );  
   printf( "\nProgram takes %6.0f seconds.\n", elapsed_time );  
}  
  
```  
  
```Output  
Using random floating point numbers 1.04749e+038 2.01482e+038 1.72737e+038Multiplying 2 floating point numbers 100 million times...Program takes      3 seconds.Multiplying 2 floating point numbers 500 million times...  
  
Program takes      5 seconds.  
```  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [時間管理](../../c-runtime-library/time-management.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)
