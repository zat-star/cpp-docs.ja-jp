---
title: "localtime_s、_localtime32_s、_localtime64_s | Microsoft Docs"
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
  - "_localtime64_s"
  - "_localtime32_s"
  - "localtime_s"
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
  - "_localtime32_s"
  - "localtime32_s"
  - "localtime_s"
  - "localtime64_s"
  - "_localtime64_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_localtime64_s 関数"
  - "localtime32_s 関数"
  - "_localtime32_s 関数"
  - "localtime64_s 関数"
  - "時間、値の変換"
  - "localtime_s 関数"
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# localtime_s、_localtime32_s、_localtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

時刻の値を変換し、ローカル タイム ゾーンを修正します。 これらのバージョンは、 [localtime、\_localtime32、\_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 」の説明に従って、セキュリティ強化機能を備えた [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)します。  
  
## 構文  
  
```  
errno_t localtime_s(  
   struct tm* _tm,  
   const time_t *time   
);  
errno_t _localtime32_s(  
   struct tm* _tm,  
   const time32_t *time   
);  
errno_t _localtime64_s(  
   struct tm* _tm,  
   const _time64_t *time   
);  
```  
  
#### パラメーター  
 `_tm`  
 入力する時間の構造体へのポインター。  
  
 `time`  
 格納されている時刻へのポインター。  
  
## 戻り値  
 正常終了した場合は 0 を返します。 戻り値は、障害が発生した場合、エラー コードです。 エラー コードは、Errno.h で定義されます。 これらのエラーの一覧については、次を参照してください。 [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)します。  
  
### エラー条件  
  
|`_tm`|`time`|戻り値|値します。 `_tm`|無効なパラメーター ハンドラーが呼び出されます|  
|-----------|------------|---------|-----------------|-----------------------------|  
|`NULL`|任意|`EINVAL`|変更されません。|はい|  
|いない `NULL` \(有効なメモリを指す\)|`NULL`|`EINVAL`|すべてのフィールドが\-1 に設定します。|はい|  
|いない `NULL` \(有効なメモリを指す\)|0 より小さいかより大きい `_MAX__TIME64_T`|`EINVAL`|すべてのフィールドが\-1 に設定します。|Ｘ|  
  
 」の説明に従って、最初の 2 つのエラー条件の場合、無効なパラメーター ハンドラーが呼び出される [パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## 解説  
 `_localtime32_s` 関数として格納されている時刻の変換、 [time\_t](../../c-runtime-library/standard-types.md) 値し、結果の種類の構造に格納 `tm`します。`long` 値 `timer` 午前 0 時からの経過秒数を表します \(00: 00:00\)、1970 年 1 月 1 日 \(utc\)。 この値は、通常の取得、 `time` 関数です。  
  
 `_localtime32_s` ユーザーが最初にグローバル環境変数を設定する場合は、ローカル タイム ゾーンの修正 `TZ`します。`TZ` 設定すると、その他の 3 つの環境変数 \(`_timezone`, 、`_daylight`, 、および `_tzname`\) も自動的に設定します。 場合、 `TZ` 変数が設定されていない `localtime32_s` コントロール パネルの \[日付\/時刻で指定されているタイム ゾーン情報を使用します。 この情報を取得できない既定では太平洋標準時タイム ゾーンを表す PST8PDT が使用されます。 参照してください [\_tzset](../Topic/_tzset.md) これらの変数の詳細についてです。`TZ` Microsoft 拡張機能との ANSI 標準の定義の一部ではない `localtime`します。  
  
> [!NOTE]
>  ターゲット環境は、夏時間が有効になっているかどうかを判断するください。  
  
 `_localtime64_s`, 、が使用される、 `__time64_t` 構造体での日付を世界協定時刻 \(UTC\) で 3000 年 12 月 31 日 23時 59分分 59 秒を表す一方 `_localtime32_s` の 2038 年 1 月 18 日 23時 59分: 59 までの日付を表します。  
  
 `localtime_s` 評価されるインライン関数は、 `_localtime64_s`, 、および `time_t` は `__time64_t`です。 コンパイラが `time_t` を古い 32 ビットの `time_t` として解釈するよう強制する必要がある場合には、`_USE_32BIT_TIME_T` を定義します。 これにより、その `localtime_s` を評価する `_localtime32_s`です。 2038 年 1 月 18 日後に、アプリケーションが失敗して、64 ビット プラットフォーム上で許可されていないために、この操作は推奨されません。  
  
 構造体の型のフィールド [tm](../../c-runtime-library/standard-types.md) それぞれが、次の値を格納、 `int`です。  
  
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
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`localtime_s`|\<time.h\>|  
|`_localtime32_s`|\<time.h\>|  
|`_localtime64_s`|\<time.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_localtime_s.c  
/* This program uses _time64 to get the current time   
 * and then uses _localtime64_s() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
        char timebuf[26];  
        errno_t err;  
  
        // Get time as 64-bit integer.  
        _time64( &long_time );   
        // Convert to local time.  
        err = _localtime64_s( &newtime, &long_time );   
        if (err)  
        {  
            printf("Invalid argument to _localtime64_s.");  
            exit(1);  
        }  
        if( newtime.tm_hour > 12 )        // Set up extension.   
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime.tm_hour > 12 )        // Convert from 24-hour   
                newtime.tm_hour -= 12;    // to 12-hour clock.   
        if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime.tm_hour = 12;  
  
        // Convert to an ASCII representation.   
        err = asctime_s(timebuf, 26, &newtime);  
        if (err)  
        {  
           printf("Invalid argument to asctime_s.");  
           exit(1);  
        }  
        printf( "%.19s %s\n", timebuf, am_pm );  
}  
```  
  
## 出力例  
  
```  
Fri Apr 25 01:19:27 PM  
```  
  
## 同等の .NET Framework 関数  
 [System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime\_s、\_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime、\_ctime32、\_ctime64、\_wctime、\_wctime32、\_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s、\_gmtime32\_s、\_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime、\_localtime32、\_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)