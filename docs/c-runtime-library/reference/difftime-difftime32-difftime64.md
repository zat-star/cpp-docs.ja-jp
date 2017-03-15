---
title: "difftime、_difftime32、_difftime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_difftime32"
  - "difftime"
  - "_difftime64"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_difftime64"
  - "difftime"
  - "difftime64"
  - "_difftime32"
  - "difftime32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_difftime32 関数"
  - "difftime 関数"
  - "時間、差異の検出"
  - "difftime64 関数"
  - "_difftime64 関数"
  - "difftime32 関数"
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# difftime、_difftime32、_difftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2 つの時刻の差を検索します。  
  
## 構文  
  
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
  
#### パラメーター  
 `timer1`  
 終了時刻。  
  
 `timer0`  
 開始時刻。  
  
## 戻り値  
 `difftime` 経過時間を秒単位でから返します `timer0` に `timer1`します。 返される値は、倍精度浮動小数点数です。 戻り値には、エラーを示す 0 を指定できます。  
  
## 解説  
 `difftime` 関数は、2 つの指定された時間値の差を計算 `timer0` と `timer1`です。  
  
 指定した時刻の値が範囲に収まる必要があります `time_t`します。`time_t` 64 ビット値です。 このため、範囲の末尾 23時 59分: 59 から 2038 年 1 月 18 日 \(utc\) に拡張 3000 年 12 月 31 日 23時 59分: 59 秒です。 範囲の `time_t` が 1970 年 1 月 1 日午前 0 時です。  
  
 `difftime` いずれかに評価されるインライン関数は、 `_difftime32` または `_difftime64` かどうかによって `_USE_32BIT_TIME_T` が定義されています。 \_difftime32、\_difftime64 時の型の特定のサイズの使用を強制するには、直接使用できます。  
  
 これらの関数では、パラメーターの検証が行われます。 場合のパラメーターが 0 または負の場合、無効なパラメーター ハンドラーが呼び出される」の説明に従って [パラメーターの検証](../../c-runtime-library/parameter-validation.md)します。 実行の継続が許可された場合、これらの関数は 0 を返します設定と `errno` に `EINVAL`します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`difftime`|\<time.h\>|  
|`_difftime32`|\<time.h\>|  
|`_difftime64`|\<time.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
1.04749e + 038 2.01482e + 038 1.72737e + 038Multiplying 番号をランダムな浮動小数点を使用して 2 つの浮動小数点数値 100 100万回.プログラムでは、3 秒を取得します。浮動小数点乗算の 2 では、500 100万回の数値をポイントしています.プログラムでは、5 秒を取得します。  
```  
  
## 同等の .NET Framework 関数  
 [System::DateTime::Subtract](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [時間管理](../../c-runtime-library/time-management.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)