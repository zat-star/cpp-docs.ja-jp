---
title: "_mkgmtime、_mkgmtime32、_mkgmtime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mkgmtime32"
  - "_mkgmtime64"
  - "_mkgmtime"
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
  - "_mkgmtime64"
  - "mkgmtime32"
  - "_mkgmtime32"
  - "mkgmtime"
  - "mkgmtime64"
  - "_mkgmtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mkgmtime32 関数"
  - "時間関数"
  - "mkgmtime 関数"
  - "_mkgmtime 関数"
  - "変換 (時間を)"
  - "mkgmtime64 関数"
  - "_mkgmtime64 関数"
  - "_mkgmtime32 関数"
  - "時間、変換"
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _mkgmtime、_mkgmtime32、_mkgmtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

によって表される UTC 時刻に変換、 `tm``struct` を UTC 時刻で表される、 `time_t` 型です。  
  
## 構文  
  
```  
  
time_t _mkgmtime(  
   struct tm*   
timeptr  
);  
__time32_t _mkgmtime32(  
   struct tm*   
timeptr  
);  
__time64_t _mkgmtime64(  
   struct tm*   
timeptr  
);  
  
```  
  
#### パラメーター  
 `timeptr`  
 UTC 時刻としてへのポインター、 `struct``tm` に変換します。  
  
## 戻り値  
 型の数量 `__time32_t` または `__time64_t` 世界協定時刻 \(UTC\) で 1970 年 1 月 1 日午前 0 時から経過した秒数を表します。 日付が範囲外にある場合 \(「解説」セクションを参照してください\) または入力は、有効な時刻として解釈できない場合、戻り値は\-1。  
  
## 解説  
 `_mkgmtime32` と `_mkgmtime64` の関数には、UTC 時刻の変換、 `__time32_t` または `__time64_t` UTC 時刻を表す型。 ローカル時刻を UTC 時刻に変換するには使用 `mktime`, 、`_mktime32`, 、および `_mktime64` 代わりにします。  
  
 `_mkgmtime` 評価されるインライン関数は、 `_mkgmtime64`, 、および `time_t` は `__time64_t`です。 強制的にコンパイラを解釈する必要がある場合 `time_t`従来の 32 ビットとして `time_t`, 、定義する `_USE_32BIT_TIME_T`です。 これは、は 2038 年 1 月 18 日後、アプリケーションが失敗するため、推奨されませんが \(32 ビットの最大範囲 `time_t`\)、64 ビット プラットフォーム上で許可されていないとします。  
  
 構造体が渡された時間は変更次のように同じ方法で、変更されると、 `_mktime` 関数: `tm_wday` と `tm_yday` フィールドの値に基づいて新しい値に設定されます `tm_mday` と `tm_year`です。`tm` 構造体時間を指定するときは、`tm_isdst` フィールドを次のように設定します。  
  
-   標準時間が有効であることを示す場合はゼロ \(0\)。  
  
-   夏時間が有効であることを示す場合は 0 より大きい値。  
  
-   標準時間と夏時間のどちらが有効であるかを C ランタイム ライブラリ コードで計算する場合は 0 より小さい値。  
  
 C ランタイム ライブラリでは、TZ 環境変数を使用して、正しい夏時間を調べます。 TZ が設定されていない場合、オペレーティング システムが正しい夏時間時の動作を取得する照会されます。`tm_isdst` は必須フィールドです。 かどうかは設定されていない、その値は未定義とからの戻り値 `mktime` は予測できません。  
  
 範囲、 `_mkgmtime32` 関数は 1970 年 1 月 1 日午前 0 時から 2038 年 1 月 18 日 23時 59分: 59 まで \(utc\)。 範囲 `_mkgmtime64` が 1970 年 1 月 1 日午前 0 時 \(utc\) から 3000 年 12 月 31 日 23時 59分: 59 秒 \(utc\)。 範囲外の日付は、戻り値 – 1 になります。 範囲 `_mkgmtime` かどうかによって異なります `_USE_32BIT_TIME_T` が定義されています。 \(既定値\) が定義されていない場合、範囲は `_mkgmtime64`、それ以外の範囲の 32 ビットの範囲に制限されて `_mkgmtime32`します。  
  
 `gmtime` と `localtime` 変換に 1 つの静的に割り当てられたバッファーを使用します。 このバッファーを指定する場合は、 `mkgmtime`, 、以前の内容は破棄されます。  
  
## 使用例  
  
```  
// crt_mkgmtime.c  
#include <stdio.h>  
#include <time.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t now, mytime, gmtime;  
    char buff[30];  
  
    time( & now );  
  
    _localtime64_s( &t1, &now );  
    _gmtime64_s( &t2, &now );  
  
    mytime = mktime(&t1);  
    gmtime = _mkgmtime(&t2);  
  
    printf("Seconds since midnight, January 1, 1970\n");  
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);  
  
    /* Use asctime_s to display these times. */  
  
    _localtime64_s( &t1, &mytime );  
    asctime_s( buff, sizeof(buff), &t1 );  
    printf( "Local Time: %s\n", buff );  
  
    _gmtime64_s( &t2, &gmtime );  
    asctime_s( buff, sizeof(buff), &t2 );  
    printf( "Greenwich Mean Time: %s\n", buff );  
  
}  
```  
  
## 出力例  
  
```  
Seconds since midnight, January 1, 1970  
My time: 1171588492  
GM time (UTC): 1171588492  
  
Local Time: Thu Feb 15 17:14:52 2007  
  
Greenwich Mean Time: Fri Feb 16 01:14:52 2007  
```  
  
 次の例では、不完全な構造体型は、曜日、年の日の計算値で埋め方法を示します。  
  
```  
// crt_mkgmtime2.c  
#include <stdio.h>  
#include <time.h>  
#include <memory.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t gmtime;  
    char buff[30];  
  
    memset(&t1, 0, sizeof(struct tm));  
    memset(&t2, 0, sizeof(struct tm));  
  
    t1.tm_mon = 1;  
    t1.tm_isdst = 0;  
    t1.tm_year = 103;  
    t1.tm_mday = 12;  
  
    // The day of the week and year will be incorrect in the output here.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
    gmtime = _mkgmtime(&t1);  
  
    // The correct day of the week and year were determined.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
}  
```  
  
## 出力  
  
```  
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003  
 t.tm_yday = 0  
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003  
 t.tm_yday = 42  
```  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、\_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime\_s、\_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime\_s、\_gmtime32\_s、\_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s、\_localtime32\_s、\_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime、\_mktime32、\_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)