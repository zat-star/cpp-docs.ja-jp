---
title: "_ftime_s、_ftime32_s、_ftime64_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftime_s
- _ftime64_s
- _ftime32_s
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
- _ftime_s
- _ftime64_s
- ftime_s
- _ftime32_s
- ftime32_s
- ftime64_s
dev_langs:
- C++
helpviewer_keywords:
- ftime32_s function
- ftime_s function
- _ftime64_s function
- current time
- ftime64_s function
- time, getting current
- _ftime_s function
- _ftime32_s function
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
caps.latest.revision: 24
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 20611bb1f40ae900ad2653395da6a0d8279252db
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="ftimes-ftime32s-ftime64s"></a>_ftime_s、_ftime32_s、_ftime64_s
現在の時刻を取得します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」で説明されているように、セキュリティが強化されたバージョンの [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _ftime_s(   
   struct _timeb *timeptr   
);  
errno_t _ftime32_s(   
   struct __timeb32 *timeptr   
);  
errno_t _ftime64_s(   
   struct __timeb64 *timeptr   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `timeptr`  
 ポインター、 `_timeb`、 `__timeb32`、または`__timeb64`構造体。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 `timeptr` が `NULL` の場合、戻り値は `EINVAL` です。  
  
## <a name="remarks"></a>コメント  
 `_ftime_s`関数は、現在の現地時刻を取得しが指す構造体に格納`timeptr`です。 `_timeb`、 `__timeb32`、および`__timeb64`SYS\Timeb.h で定義されます。 これらは、次の表に示す 4 つのフィールドを含んでいます。  
  
 `dstflag`  
 ローカルのタイム ゾーンで夏時間が現在有効になっている場合は 0 以外の値です  (夏時間を判断する方法の詳細については、[_tzset](../../c-runtime-library/reference/tzset.md) を参照してください)。  
  
 `millitm`  
 ミリ秒単位での秒の小数部。  
  
 `time`  
 世界協定時刻 (UTC: Coordinated Universal Time) の 1970 年 1 月 1 日の深夜 00:00:00 から経過した時間 (秒単位)。  
  
 `timezone`  
 西に移動するときの UTC と現地時刻の間の差 (分単位)。 `timezone` の値は、グローバル変数 `_timezone` の値から設定されます (`_tzset` を参照してください)。  
  
 `__timeb64` 構造体を使用する `_ftime64_s` は、UTC の 3000 年 12 月 31 日の 23 時 59 分 59 秒までのファイル作成日付を表すことができます。それに対して、`_ftime32_s` は、UTC の 2038 年 1 月 18 日の 23 時 59 分 59 秒までしか表すことができません。 これらの関数の日付範囲の下限は、いずれも 1970 年 1 月 1 日の午前 0 時です。  
  
 `_ftime_s` は `_ftime64_s` と同等で、`_timeb` には 64 ビットの時刻が含まれます。 これは、`_USE_32BIT_TIME_T` が定義されていない場合に当てはまります。定義されている場合には、古い動作が有効になります。`_ftime_s` は 32 ビットの時刻を使用します。`_timeb` には 32 ビットの時刻が含まれます。  
  
 `_ftime_s` はそのパラメーターを検証します。 `timeptr` として null ポインターが渡された場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、関数は `errno` を `EINVAL` に設定します。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_ftime_s`|\<sys/types.h> と \<sys/timeb.h>|  
|`_ftime32_s`|\<sys/types.h> と \<sys/timeb.h>|  
|`_ftime64_s`|\<sys/types.h> と \<sys/timeb.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_ftime64_s.c  
// This program uses _ftime64_s to obtain the current  
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
  
   _ftime64_s( &timebuffer );  
  
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
  
```Output  
Seconds since midnight, January 1, 1970 (UTC): 1051553334  
Milliseconds: 230  
Minutes between UTC and local time: 480  
Daylight savings time flag (1 means Daylight time is in effect): 1  
The time is Mon Apr 28 11:08:54.230 2003  
```  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)
