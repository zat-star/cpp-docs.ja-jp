---
title: "localtime、_localtime32、_localtime64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _localtime64
- _localtime32
- localtime
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
dev_langs: C++
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 77a0a297413c053dee3e165ece07034487535b06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="localtime-localtime32-localtime64"></a>localtime、_localtime32、_localtime64
時刻値を変換し、ローカル タイム ゾーンに合わせて修正します。 これらの関数にはセキュリティを強化したバージョンがあります。[localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) を参照してください。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `timer`  
 格納されている時刻へのポインター。  
  
## <a name="return-value"></a>戻り値  
 構造体の結果へのポインターを返すか、関数に渡された日付が次の場合は `NULL` を返します。  
  
-   1970 年 1 月 1 日午前 0 時より前。  
  
-   UTC の 2038 年 1 月 19 日 3 時 14 分 07 秒より後 (`_time32` と `time32_t` を使用)。  
  
-   UTC の 3000 年 12 月 31 日 23 時 59 分 59 秒より後 (`_time64` と `__time64_t` を使用)。  
  
 `_localtime64` では `__time64_t` 構造体を使用し、協定世界時 (UTC) の 3000 年 12 月 31 日の 23 時 59 分 59 秒までの日付を表すことができます。それに対して、`_localtime32` は、UTC の 2038 年 1 月 18 日の 23 時 59 分 59 秒までを表します。  
  
 `localtime` は `_localtime64` と評価されるインライン関数であり、`time_t` は `__time64_t` と等価です。 コンパイラが `time_t` を古い 32 ビットの `time_t`として解釈するよう強制する必要がある場合には、 `_USE_32BIT_TIME_T`を定義します。 これにより、`localtime` の値は `_localtime32` になります。 ただし、この方法は推奨されません。2038 年 1 月 18 日以降にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。  
  
 構造体の型 [tm](../../c-runtime-library/standard-types.md) のフィールドは次の値を格納します。値はそれぞれ `int` です。  
  
 `tm_sec`  
 秒 (0 ~ 59)。  
  
 `tm_min`  
 分 (0 ~ 59)。  
  
 `tm_hour`  
 午前 0 時以降後の時間 (0 ~ 23)。  
  
 `tm_mday`  
 (1 ~ 31) の月の日です。  
  
 `tm_mon`  
 月 (0 ~ 11 です。年 1 月 = 0) です。  
  
 `tm_year`  
 年 (実際の西暦から 1900 を引いた数)  
  
 `tm_wday`  
 曜日 (0 ~ 6 です。日曜日 = 0) です。  
  
 `tm_yday`  
 年の日付 (0 ~ 365 です。1 月 1 日 = 0) です。  
  
 `tm_isdst`  
 夏時間が有効な場合は正の値、夏時間が無効な場合は 0、夏時間かどうか状態が不明な場合は負の値。 `TZ` 環境変数が設定されている場合、C ランタイム ライブラリでは、米国に適合した規則を前提に夏時間 (DST) を計算します。  
  
## <a name="remarks"></a>コメント  
 `localtime` 関数は [time_t](../../c-runtime-library/standard-types.md) 値として格納されている時間を変換して、その結果を `tm` 型として格納します。 `long` 型の値 `timer` は、UTC の 1970 年 1 月 1 日午前 0 時 (00:00:00) からの経過秒数を表します。 通常、この値は `time` 関数で取得されます。  
  
 32 ビット バージョンおよび 64 ビット バージョンの `gmtime`、`mktime`、`mkgmtime`、`localtime` の各関数はすべて、1 スレッドあたり `tm` 構造体を 1 つ使用して変換を行います。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。  
  
 `localtime` は、ユーザーが最初にグローバル環境変数 `TZ` を設定している場合、ローカル タイム ゾーンに合わせて修正します。 `TZ` を設定すると、他の 3 つの環境変数 (`_timezone`、`_daylight`、`_tzname`) も自動的に設定されます。 `TZ` 変数が設定されていない場合、`localtime` は [コントロール パネル] の [日付/時刻] アプリケーションで指定されているタイム ゾーンの情報を使用しようとします。 この情報を取得できない場合、既定では、太平洋タイム ゾーンを表す PST8PDT が使用されます。 これらの変数の説明については、[_tzset](../../c-runtime-library/reference/tzset.md) を参照してください。 `TZ` は、Microsoft 拡張機能であり、`localtime` の ANSI 標準定義の一部ではありません。  
  
> [!NOTE]
>  対象の環境は、夏時間が有効かどうかを判断しようとします。  
  
 これらの関数では、パラメーターの検証が行われます。 `timer` が null ポインターの場合またはタイマー値が負の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`localtime`|\<time.h>|  
|`_localtime32`|\<time.h>|  
|`_localtime64`|\<time.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
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
Tue Feb 12 10:05:58 AM  
```  
  
## <a name="see-also"></a>参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)