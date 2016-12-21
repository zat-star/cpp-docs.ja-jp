---
title: "_ftime、_ftime32、_ftime64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ftime64"
  - "_ftime"
  - "_ftime32"
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
  - "_ftime32"
  - "_ftime"
  - "_ftime64"
  - "ftime64"
  - "ftime"
  - "ftime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ftime64 関数"
  - "_ftime64 関数"
  - "現在時刻"
  - "_ftime 関数"
  - "ftime 関数"
  - "_ftime32 関数"
  - "ftime32 関数"
  - "時刻、取得 (現在の)"
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
caps.latest.revision: 27
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ftime、_ftime32、_ftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在の時刻を取得します。  これらの関数のセキュリティを強化したバージョンについては、「[\_ftime\_s、\_ftime32\_s、\_ftime64\_s](../Topic/_ftime_s,%20_ftime32_s,%20_ftime64_s.md)」を参照してください。  
  
## 構文  
  
```  
void _ftime(   
   struct _timeb *timeptr   
);  
void _ftime32(   
   struct __timeb32 *timeptr   
);  
void _ftime64(   
   struct __timeb64 *timeptr   
);  
```  
  
#### パラメーター  
 `timeptr`  
 `_timeb`、`__timeb32` または `__timeb64` 構造体へのポインター。  
  
## 解説  
 `_ftime` 関数は、現在の現地時刻を受け取り、`timeptr`が指す構造体に格納します*。*`_timeb`、`__timeb32`と`__timeb64` 構造体は SYS\\Timeb.h で定義されます。  これらを次の表に示す 4 種類のフィールドが含まれています。  
  
 `dstflag`  
 夏時間がローカル タイム ゾーンの場合、現在の 0 以外の。夏時間の指定方法のか \(説明の [\_tzset](../Topic/_tzset.md) を参照してください\)。  
  
 `millitm`  
 ミリ秒のほんの一瞬。  
  
 `time`  
 深夜 00:00 時以降の経過時間: 00\)、1970 年 1 月 1 日 1 時の世界協定時刻 \(UTC\)。  
  
 `timezone`  
 UTC と現地時間中、西方に移動する分の差を計算します。  `timezone` の値がグローバル変数 `_timezone` の値に設定されます。`_tzset`を参照してください。  
  
 `_ftime64`は `__timeb64` 構造体を使用する作成日を 23:59 によって表される \(: 59、3000 12 年 10 月 31 日は、UTC; `_ftime32` が 03:14 だけで日付を表す場合: 1 年 1 月 07 日 19 時 2038、UTC。  午前 1970 は 1 年 1 月 1 日、これらすべての関数の日付範囲の下限です。  
  
 `_ftime` は `_ftime64` と等価であり、`_timeb` は 64 ビットの時刻が格納されます。  これは、古い動作が有効な場合 `_USE_32BIT_TIME_T` が定義されていない場合に、; `_ftime` は 32 ビットの時刻を使用し、`_timeb` は 32 ビットの時刻が格納されます。  
  
 `_ftime` はそのパラメーターを検証します。  null ポインターは [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように `timeptr`渡られたら関数として、無効なパラメーター ハンドラーを呼び出します。  実行の継続 `EINVAL`に関数を設定 `errno`。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_ftime`|\<sys\/types.h と\> sys \<\/timeb.h\>|  
|`_ftime32`|\<sys\/types.h と\> sys \<\/timeb.h\>|  
|`_ftime64`|\<sys\/types.h と\> sys \<\/timeb.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_ftime.c  
// compile with: /W3  
// This program uses _ftime to obtain the current  
// time and then stores this time in timebuffer.  
  
#include <stdio.h>  
#include <sys/timeb.h>  
#include <time.h>  
  
int main( void )  
{  
   struct _timeb timebuffer;  
   char timeline[26];  
   errno_t err;  
   time_t time1;  
   unsigned short millitm1;  
   short timezone1;  
   short dstflag1;  
  
   _ftime( &timebuffer ); // C4996  
   // Note: _ftime is deprecated; consider using _ftime_s instead  
  
   time1 = timebuffer.time;  
   millitm1 = timebuffer.millitm;  
   timezone1 = timebuffer.timezone;  
   dstflag1 = timebuffer.dstflag;  
  
   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",   
   time1);  
   printf( "Milliseconds: %d\n", millitm1);  
   printf( "Minutes between UTC and local time: %d\n", timezone1);  
   printf( "Daylight savings time flag (1 means Daylight time is in "  
           "effect): %d\n", dstflag1);   
  
   err = ctime_s( timeline, 26, & ( timebuffer.time ) );  
   if (err)  
   {  
       printf("Invalid argument to ctime_s. ");  
   }  
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,  
           &timeline[20] );  
}  
```  
  
  **午前 1970 年 1 月 1 日 1 時以降の経過秒 \(UTC\) : 1051553334**  
**ミリ秒: 230**  
**UTC と現地時間間の分: 480**  
**夏時間フラグ \(1 は夏時間が有効な\) : 1**  
**" time が 4 年 1 月 28 日の 11:08: 54.230、2003 年\)**    
## 同等の .NET Framework 関数  
 [System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、\_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime、\_ctime32、\_ctime64、\_wctime、\_wctime32、\_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、\_localtime32、\_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)