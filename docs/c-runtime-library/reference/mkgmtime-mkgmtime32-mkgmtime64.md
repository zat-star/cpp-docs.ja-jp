---
title: "_mkgmtime、_mkgmtime32、_mkgmtime64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
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
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
dev_langs: C++
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f99e367d263d3ba49837b269fd04159a70cf549
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mkgmtime-mkgmtime32-mkgmtime64"></a>_mkgmtime、_mkgmtime32、_mkgmtime64
`tm struct` によって表される UTC 時刻を、`time_t` 型で表される UTC 時刻に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      time_t _mkgmtime(  
   struct tm* timeptr  
);  
__time32_t _mkgmtime32(  
   struct tm* timeptr  
);  
__time64_t _mkgmtime64(  
   struct tm* timeptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `timeptr`  
 変換する `struct tm` としての UTC 時刻へのポインター。  
  
## <a name="return-value"></a>戻り値  
 協定世界時 (UTC) で 1970 年 1 月 1 日午前 0 時以降の経過秒数を表す、`__time32_t` 型または `__time64_t` 型の数。 日付が範囲外の場合 (「解説」セクションを参照してください) または入力、有効な時刻として解釈できない場合、戻り値は-1。  
  
## <a name="remarks"></a>コメント  
 `_mkgmtime32` と `_mkgmtime64` 関数は UTC 時刻を変換して、`__time32_t` 型または `__time64_t` 型によってその時刻を UTC で表します。 現地時刻を UTC 時刻に変換するには、代わりに `mktime`、`_mktime32`、`_mktime64` を使用します。  
  
 `_mkgmtime` は `_mkgmtime64` と評価されるインライン関数であり、`time_t` は `__time64_t` と等価です。 コンパイラが `time_t` を古い 32 ビットの `time_t`として解釈するよう強制する必要がある場合には、 `_USE_32BIT_TIME_T`を定義します。 この方法はお勧めしません。2038 年 1 月 18 日 (32 ビット `time_t` の最大範囲) より後にアプリケーションがエラーになる可能性があり、また、どの 64 ビット プラットフォームでも使用できないためです。  
  
 渡される時間の構造体は、`_mktime` 関数の場合と同様に次のように変更されます。`tm_wday` フィールドと `tm_yday` フィールドは `tm_mday` と `tm_year` の値に基づいて新しい値に設定されます。 `tm` 構造体時間を指定するときは、`tm_isdst` フィールドを次のように設定します。  
  
-   標準時間が有効であることを示す場合はゼロ (0)。  
  
-   夏時間が有効であることを示す場合は 0 より大きい値。  
  
-   標準時間と夏時間のどちらが有効であるかを C ランタイム ライブラリ コードで計算する場合は 0 より小さい値。  
  
 C ランタイム ライブラリは、TZ 環境変数を使用して、正しい夏時間を特定します。 TZ が設定されていない場合は、オペレーティング システムに照会して、正しい地域の夏時間の動作を取得します。 `tm_isdst` は必須フィールドです。 設定しないと、その値は未定義になり、`mktime` からの戻り値は予測できません。  
  
 `_mkgmtime32` 関数の範囲は、UTC の 1970 年 1 月 1 日午前 0 時から UTC の 2038 年 1 月 18 日 23 時 59 分 59 秒までです。 `_mkgmtime64` の範囲は、UTC の 1970 年 1 月 1 日午前 0 時から UTC の 3000 年 12 月 31 日 23 時 59 分 59 秒までです。 範囲外の日付は、戻り値-1 になります。 `_mkgmtime` の範囲は、`_USE_32BIT_TIME_T` が定義されているかどうかによって変わります。 定義されていない場合 (既定)、範囲は `_mkgmtime64` の範囲と同じです。定義されている場合は、32 ビットの `_mkgmtime32` の範囲に限定されます。  
  
 `gmtime` と `localtime` は、静的に割り当てられた単一のバッファーを使用して変換を行うことにご注意ください。 `mkgmtime` にこのバッファーを指定すると、以前の内容は破棄されます。  
  
## <a name="example"></a>例  
  
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
  
## <a name="sample-output"></a>出力例  
  
```  
Seconds since midnight, January 1, 1970  
My time: 1171588492  
GM time (UTC): 1171588492  
  
Local Time: Thu Feb 15 17:14:52 2007  
  
Greenwich Mean Time: Fri Feb 16 01:14:52 2007  
```  
  
 未完成の構造体に曜日と年通算日の計算値を入力する例を次に示します。  
  
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
  
## <a name="output"></a>出力  
  
```  
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003  
 t.tm_yday = 0  
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003  
 t.tm_yday = 42  
```  
  
## <a name="see-also"></a>参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime、_mktime32、_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)