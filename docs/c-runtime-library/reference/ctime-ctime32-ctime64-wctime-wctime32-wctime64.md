---
title: "ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64 | Microsoft Docs"
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
  - "_ctime64"
  - "_wctime32"
  - "ctime"
  - "_wctime64"
  - "_ctime32"
  - "_wctime"
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
  - "_wctime64"
  - "_ctime32"
  - "_tctime"
  - "_wctime"
  - "_wctime32"
  - "_tctime64"
  - "_ctime64"
  - "ctime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tctime64 関数"
  - "_ctime32 関数"
  - "ctime32 関数"
  - "_wctime 関数"
  - "wctime64 関数"
  - "_tctime64 関数"
  - "_tctime32 関数"
  - "_ctime64 関数"
  - "_wctime64 関数"
  - "ctime 関数"
  - "wctime32 関数"
  - "ctime64 関数"
  - "_wctime32 関数"
  - "_tctime 関数"
  - "tctime32 関数"
  - "tctime 関数"
  - "wctime 関数"
  - "時間、変換"
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

時刻の値を文字列に変換し、ローカル タイム ゾーンの設定を調整します。 これらの関数のより安全なバージョンがあります。参照してください [ctime\_s、\_ctime32\_s、\_ctime64\_s、\_wctime\_s、\_wctime32\_s、\_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)します。  
  
## 構文  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### パラメーター  
 `timer`  
 格納されている時刻へのポインター。  
  
## 戻り値  
 結果の文字列へのポインター。`NULL` 場合に返されます。  
  
-   `time` 1970 年 1 月 1 日午前 0 時 \(utc\) より前に、の日付を表します。  
  
-   使用する場合 `_ctime32` または `_wctime32` と `time` 23時 59分: 59 以後 2038 年 1 月 18 日 \(utc\) 日付を表します。  
  
-   使用する場合 `_ctime64` または `_wctime64` と `time` UTC 3000 年 12 月 31 日 23時 59分: 59 秒後の日付を表します。  
  
 `ctime` 評価されるインライン関数は、 `_ctime64` と `time_t` は `__time64_t`です。 強制的にコンパイラを解釈する必要がある場合 `time_t` 従来の 32 ビットとして `time_t`, 、定義する `_USE_32BIT_TIME_T`です。 これにより、その `ctime` を評価する `_ctime32`です。 2038 年 1 月 18 日後に、アプリケーションが失敗して、64 ビット プラットフォーム上で許可されていないために、この操作は推奨されません。  
  
## 解説  
 `ctime` 関数として格納されている時刻値に変換する [time\_t](../../c-runtime-library/standard-types.md) を文字列値。`timer` 値は、通常の呼び出しから取得 [時間](../Topic/time,%20_time32,%20_time64.md), 、午前 0 時から経過した秒数を返します \(00: 00:00\)、世界協定時刻 \(UTC\) 1970 年 1 月 1 日です。 戻り値の文字列では、26 文字であり、形式は。  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24 時間制が使用されます。 すべてのフィールドを持つ定数の幅。 文字列の最後の 2 つの位置は、改行文字 \('\\n'\) と null 文字 \('\\0'\) で使用します。  
  
 変換された文字列は、ローカル タイム ゾーンの設定に従っても調整します。 参照してください、 `time`, 、[\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), 、および [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 関数のローカル時刻を構成する方法について、 [\_tzset](../Topic/_tzset.md) の詳細については、タイム ゾーンの環境とグローバル変数を定義する関数。  
  
 呼び出し `ctime` で使用される 1 つの静的に割り当てられたバッファーの変更、 `gmtime` と `localtime` 関数です。 これらのルーチンの 1 つの各呼び出しでは、前の呼び出しの結果を破棄します。`ctime` 使用して、静的バッファーを共有、 `asctime` 関数です。 呼び出しではこのため、 `ctime` を前の呼び出しの結果は破棄 `asctime`, 、`localtime`, 、または `gmtime`です。  
  
 `_wctime` `_wctime64` のワイド文字バージョン `ctime` と `_ctime64`; ワイド文字列へのポインターを返します。 それ以外の場合、 `_ctime64`, 、`_wctime`, 、および `_wctime64` と同様に動作 `ctime`します。  
  
 これらの関数では、パラメーターの検証が行われます。 場合 `timer` 」の説明に従って、これらの関数が無効なパラメーター ハンドラーを呼び出しますタイマー値が負の場合は、null ポインター、または [パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`ctime`|\<time.h\>|  
|`_ctime32`|\<time.h\>|  
|`_ctime64`|\<time.h\>|  
|`_wctime`|\< time.h \> または \< wchar.h \>|  
|`_wctime32`|\< time.h \> または \< wchar.h \>|  
|`_wctime64`|\< time.h \> または \< wchar.h \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_ctime64.c  
// compile with: /W3  
/* This program gets the current  
 * time in _time64_t form, then uses ctime to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   __time64_t ltime;  
  
   _time64( &ltime );  
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996  
   // Note: _ctime64 is deprecated; consider using _ctime64_s  
}  
```  
  
```Output  
時間は 2 月 13 日 (水)、16時 04分: 43 2002年  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、\_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime\_s、\_ctime32\_s、\_ctime64\_s、\_wctime\_s、\_wctime32\_s、\_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、\_localtime32、\_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)