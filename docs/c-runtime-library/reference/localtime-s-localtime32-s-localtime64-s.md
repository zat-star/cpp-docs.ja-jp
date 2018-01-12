---
title: "localtime_s、_localtime32_s、_localtime64_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
dev_langs: C++
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ddce7d73919e7e7942d8ddd7954ce6cbec4789fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s、_localtime32_s、_localtime64_s
時刻値を変換し、ローカル タイム ゾーンに合わせて修正します。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) で説明されているように、セキュリティが強化されたバージョンの [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) です。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `_tm`  
 目的の情報を格納する時間構造体へのポインター。  
  
 `time`  
 格納されている時刻へのポインター。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは、Errno.h で定義されています。 これらのエラー一覧については、「[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`_tm`|`time`|戻り値|`_tm` の値|無効なパラメーター ハンドラーを呼び出す|  
|-----------|------------|------------------|--------------------|---------------------------------------|  
|`NULL`|任意|`EINVAL`|変更されない|[はい]|  
|`NULL` ではありません (有効なメモリを指します)|`NULL`|`EINVAL`|すべてのフィールドが -1 に設定される|[はい]|  
|`NULL` ではありません (有効なメモリを指します)|0 より小さいか、または `_MAX__TIME64_T` を超えている|`EINVAL`|すべてのフィールドが -1 に設定される|×|  
  
 最初の 2 つのエラーの場合は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」 (パラメーターの検証) に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_localtime32_s` 関数は [time_t](../../c-runtime-library/standard-types.md) 値として格納されている時間を変換して、その結果を `tm` 型として格納します。 `long` 型の値 `timer` は、UTC の 1970 年 1 月 1 日午前 0 時 (00:00:00) からの経過秒数を表します。 通常、この値は `time` 関数で取得されます。  
  
 `_localtime32_s` は、ユーザーが最初にグローバル環境変数 `TZ` を設定している場合、ローカル タイム ゾーンに合わせて修正します。 `TZ` を設定すると、他の 3 つの環境変数 (`_timezone`、`_daylight`、`_tzname`) も自動的に設定されます。 `TZ` 変数が設定されていない場合、`localtime32_s` は [コントロール パネル] の [日付/時刻] アプリケーションでで指定されているタイム ゾーンの情報を使用しようとします。 この情報を取得できない場合、既定では、太平洋タイム ゾーンを表す PST8PDT が使用されます。 これらの変数の説明については、[_tzset](../../c-runtime-library/reference/tzset.md) を参照してください。 `TZ` は、Microsoft 拡張機能であり、`localtime` の ANSI 標準定義の一部ではありません。  
  
> [!NOTE]
>  対象の環境によって、夏時間が有効かどうか判断されます。  
  
 `__time64_t` 構造体を使用する `_localtime64_s` は、UTC の 3001 年 1 月 18 日の 23 時 59 分 59 秒までの日付を表すことができます。それに対して、`_localtime32_s` は、UTC の 2038 年 1 月 18 日の 23 時 59 分 59 秒までしか表すことができません。  
  
 `localtime_s` は `_localtime64_s` を求めるインライン関数であり、`time_t` は `__time64_t` と等価です。 コンパイラが `time_t` を古い 32 ビットの `time_t`として解釈するよう強制する必要がある場合には、 `_USE_32BIT_TIME_T`を定義します。 これにより、`localtime_s` の値は `_localtime32_s` になります。 ただし、この方法は推奨されません。2038 年 1 月 18 日以降にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。  
  
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
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`localtime_s`|\<time.h>|  
|`_localtime32_s`|\<time.h>|  
|`_localtime64_s`|\<time.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
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
  
## <a name="sample-output"></a>出力例  
  
```  
Fri Apr 25 01:19:27 PM  
```  
  
## <a name="see-also"></a>参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
