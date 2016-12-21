---
title: "localtime、_localtime32、_localtime64 | Microsoft Docs"
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
  - "_localtime64"
  - "_localtime32"
  - "localtime"
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
  - "localtime64"
  - "_localtime64"
  - "localtime32"
  - "localtime"
  - "_localtime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "localtime32 関数"
  - "_localtime32 関数"
  - "_localtime64 関数"
  - "localtime64 関数"
  - "localtime 関数"
  - "時間、値の変換"
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# localtime、_localtime32、_localtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

時刻値に変換し、ローカル タイム ゾーンの修正します。 これらの関数のより安全なバージョンがあります。参照してください [localtime\_s、\_localtime32\_s、\_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)します。  
  
## 構文  
  
```  
struct tm *localtime(  
   const time_t *timer   
);  
struct tm *_localtime32(  
   const __time32_t *timer  
);  
struct tm *_localtime64(  
   const __time64_t *timer   
);  
```  
  
#### パラメーター  
 `timer`  
 格納されている時刻へのポインター。  
  
## 戻り値  
 構造体結果へのポインターを返すか、 `NULL` 日付が関数に渡された場合は。  
  
-   1970 年 1 月 1 日午前 0 時前です。  
  
-   UTC 2038 年 1 月 19 日 03時 14分: 07 秒後 \(を使用して `_time32` と `time32_t`\)。  
  
-   UTC 3000 年 12 月 31 日 23時 59分: 59 秒後 \(を使用して `_time64` と `__time64_t`\)。  
  
 `_localtime64`, 、が使用される、 `__time64_t` 構造体での日付を世界協定時刻 \(UTC\) で 3000 年 12 月 31 日 23時 59分分 59 秒を表す一方 `_localtime32` の 2038 年 1 月 18 日 23時 59分: 59 までの日付を表します。  
  
 `localtime` 評価されるインライン関数は、 `_localtime64`, 、および `time_t` は `__time64_t`です。 強制的にコンパイラを解釈する必要がある場合 `time_t`従来の 32 ビットとして `time_t`, 、定義する `_USE_32BIT_TIME_T`です。 これにより、その `localtime` を評価する `_localtime32`です。 2038 年 1 月 18 日後に、アプリケーションが失敗して、64 ビット プラットフォーム上で許可されていないために、この操作は推奨されません。  
  
 構造体の型のフィールド [tm](../../c-runtime-library/standard-types.md) それぞれが、次の値を格納、 `int`:  
  
 `tm_sec`  
 秒 \(0 ～ 59\)。  
  
 `tm_min`  
 分 \(0 ～ 59\)。  
  
 `tm_hour`  
 午前 0 時以降後の時間 \(0 ~ 23\)。  
  
 `tm_mday`  
 日 \(1 ～ 31\)。  
  
 `tm_mon`  
 月 \(0 ～ 11、1 月 \= 0\)。  
  
 `tm_year`  
 年 \(実際の西暦から 1900 を引いた数\)  
  
 `tm_wday`  
 曜日 \(0 ～ 6、日曜日 \= 0\)。  
  
 `tm_yday`  
 年内の通算日 \(0 ～ 365、1 月 1 日 \= 0\)。  
  
 `tm_isdst`  
 夏時間が有効です。 正の値夏時間が有効ではない場合は 0夏時間の状態が不明な場合の負の値。 場合、 `TZ` 環境変数が設定されている、C ランタイム ライブラリで規則を前提 United States に適切な夏時間 \(DST\) の計算を実装するためです。  
  
## 解説  
 `localtime` として格納されている時刻を変換する関数、 [time\_t](../../c-runtime-library/standard-types.md) 値し、結果の種類の構造に格納 `tm`します。`long` 値 `timer` 午前 0 時からの経過秒数を表します \(00: 00:00\)、1970 年 1 月 1 日 \(utc\)。 この値は、通常の取得、 `time` 機能します。  
  
 32 ビットおよび 64 ビット両方のバージョン `gmtime`, 、`mktime`, 、`mkgmtime`, 、および `localtime` 、1 つを使用してすべて `tm` 変換スレッドあたり構造体。 これらのルーチンの 1 つの各呼び出しでは、前の呼び出しの結果を破棄します。  
  
 `localtime` ユーザーが最初にグローバル環境変数を設定する場合は、ローカル タイム ゾーンの修正 `TZ`します。`TZ` 設定すると、その他の 3 つの環境変数 \(`_timezone`, 、`_daylight`, 、および `_tzname`\) も自動的に設定します。 場合、 `TZ` 変数が設定されていない `localtime` コントロール パネルの \[日付\/時刻で指定されているタイム ゾーン情報を使用します。 この情報を取得できない既定では太平洋標準時タイム ゾーンを表す PST8PDT が使用されます。 参照してください [\_tzset](../Topic/_tzset.md) これらの変数の詳細についてです。`TZ` Microsoft 拡張機能との ANSI 標準の定義の一部ではない `localtime`します。  
  
> [!NOTE]
>  ターゲット環境は、夏時間が有効になっているかどうかを判断するください。  
  
 これらの関数では、パラメーターの検証が行われます。 場合 `timer` 」の説明に従って、これらの関数が、無効なパラメーター ハンドラーを呼び出しますタイマー値が負の場合は、null ポインター、または [パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`localtime`|\<time.h\>|  
|`_localtime32`|\<time.h\>|  
|`_localtime64`|\<time.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_localtime.cpp  
// compile with: /W3  
/* This program uses _time64 to get the current time   
 * and then uses localtime64() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm *newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
  
        _time64( &long_time );           // Get time as 64-bit integer.  
                                         // Convert to local time.  
        newtime = _localtime64( &long_time ); // C4996  
        // Note: _localtime64 deprecated; consider _localetime64_s  
  
        if( newtime->tm_hour > 12 )        // Set up extension.  
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime->tm_hour > 12 )        // Convert from 24-hour  
                newtime->tm_hour -= 12;    //   to 12-hour clock.  
        if( newtime->tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime->tm_hour = 12;  
  
        char buff[30];  
        asctime_s( buff, sizeof(buff), newtime );  
        printf( "%.19s %s\n", buff, am_pm );  
}  
```  
  
```Output  
Tue Feb 12 10時 05分: 58 AM  
```  
  
## 同等の .NET Framework 関数  
 [System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、\_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime、\_ctime32、\_ctime64、\_wctime、\_wctime32、\_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime\_s、\_localtime32\_s、\_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)