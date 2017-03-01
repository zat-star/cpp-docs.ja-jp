---
title: "mktime、_mktime32、_mktime64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mktime32
- mktime
- _mktime64
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
- mktime
- _mktime64
dev_langs:
- C++
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
caps.latest.revision: 25
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1f738584d525da5b7787b2ba134e7c95ddc57683
ms.lasthandoff: 02/24/2017

---
# <a name="mktime-mktime32-mktime64"></a>mktime、_mktime32、_mktime64
現地時刻をカレンダーの値に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
time_t mktime(  
   struct tm *timeptr   
);  
__time32_t _mktime32(  
   struct tm *timeptr   
);  
__time64_t _mktime64(  
   struct tm *timeptr   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *timeptr*  
 時間構造体へのポインター。「[asctime](../../c-runtime-library/reference/asctime-wasctime.md)」をご覧ください。  
  
## <a name="return-value"></a>戻り値  
 `_mktime32` は、指定されたカレンダー時間を [time_t](../../c-runtime-library/standard-types.md) 型の値としてエンコードして返します。 *timeptr* が 1970 年 1 月 1 日午前 0 時以前の日付を参照するか、カレンダー時間を表現できない場合、`_mktime32` は `time_t` 型にキャストされた -1 を返します。 `_mktime32` を使用し、*timeptr* が世界協定時刻 (UTC) の 2038 年 1 月 18 日 23:59:59 以後の日付を参照すると、`time_t` 型にキャストされた -1 を返します。  
  
 `_mktime64` は、*timeptr* が UTC の 3000 年 12 月 31 日 23:59:59 以後の日付を参照する場合、`__time64_t` 型にキャストされた -1 を返します。  
  
## <a name="remarks"></a>コメント  
 `mktime`、`_mktime32`、および `_mktime64` 関数は、*timeptr* によって示された指定の時間構造体 (不完全な場合もある) を変換し、正規化された値を持つ完全に定義された構造体にして、次にそれを `time_t` カレンダー時間値に変換します。 変換された時間のエンコーディングは、[time](../../c-runtime-library/reference/time-time32-time64.md) 関数によって返される値と同じエンコーディングになります。 *timeptr* 構造体の `tm_wday` および `tm_yday` コンポーネントの元の値は無視され、他のコンポーネントの元の値はそれぞれの通常の範囲に限定されません。  
  
 `mktime` は `_mktime64` と同等のインライン関数ですが、`_USE_32BIT_TIME_T` が定義されている場合は `_mktime32` と同等になります。  
  
 `_mktime32` は、UTC への調整後、UTC の 1970 年 1 月 1 日午前 0 時から 2038 年 1 月 18 日 23:59:59 までの日付を扱います。 `_mktime64` は、1970 年 1 月 1 日午前 0 時から 3000 年 12 月 31 日 23:59:59 までの日付を扱います。 この調整により、指定した日付が範囲内にある場合でも、これらの関数が -1 (`time_t`、`__time32_t`、または `__time64_t` にキャスト) を返す場合があります。 たとえば、エジプトのカイロにいる場合は、UTC より&2; 時間進んでいるので、*timeptr* で指定した日付から最初に&2; 時間が差し引かれます。そのため、日付が範囲外になる可能性があります。  
  
 これらの関数は、tm 構造体の検証と値の設定に使用されることがあります。 成功すると、これらの関数は `tm_wday` と `tm_yday` の値を適切に設定し、指定されたカレンダー時間を表すように他のコンポーネントを設定します。ただし、各値は通常の範囲内に限定されます。 `tm_mday` の最終的な値は、`tm_mon` と `tm_year` が決定されるまでは設定されません。 `tm` 構造体時間を指定するときは、`tm_isdst` フィールドを次のように設定します。  
  
-   標準時間が有効であることを示す場合はゼロ (0)。  
  
-   夏時間が有効であることを示す場合は 0 より大きい値。  
  
-   標準時間と夏時間のどちらが有効であるかを C ランタイム ライブラリ コードで計算する場合は&0; より小さい値。  
  
 C ランタイム ライブラリは、[TZ](../../c-runtime-library/reference/tzset.md) 環境変数から夏時間の状態を判断します。 `TZ` が設定されていない場合は、オペレーティング システムから夏時間の情報を取得するために、Win32 API 呼び出しの [GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx) が使用されます。 これが失敗すると、ライブラリは、夏時間の計算の実装にアメリカ合衆国の規則が使用されると見なします。 `tm_isdst` は必須フィールドです。 設定しないと、その値は未定義になり、これらの関数からは予想外の値が返されます。 *timeptr* が、以前の `asctime`、`gmtime`、または `localtime` (またはこれらの関数のバリアント) への呼び出しによって返された `tm` 構造体を指す場合、`tm_isdst` フィールドには正しい値が含まれています。  
  
 `gmtime` と `localtime` (および `_gmtime32`、`_gmtime64`、`_localtime32` と `_localtime64`) は、変換のために、スレッドごとに&1; つのバッファーを使用することに注意してください。 `mktime`、`_mktime32`、または `_mktime64` にこのバッファーを指定すると、以前の内容は破棄されます。  
  
 これらの関数では、パラメーターの検証が行われます。 *timeptr* が null ポインターである場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は -1 を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`mktime`|\<time.h>|  
|`_mktime32`|\<time.h>|  
|`_mktime64`|\<time.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_mktime.c  
/* The example takes a number of days  
 * as input and returns the time, the current  
 * date, and the specified number of days.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm  when;  
   __time64_t now, result;  
   int        days;  
   char       buff[80];  
  
   time( &now );  
   _localtime64_s( &when, &now );  
   asctime_s( buff, sizeof(buff), &when );  
   printf( "Current time is %s\n", buff );  
   days = 20;  
   when.tm_mday = when.tm_mday + days;  
   if( (result = mktime( &when )) != (time_t)-1 ) {  
      asctime_s( buff, sizeof(buff), &when );  
      printf( "In %d days the time will be %s\n", days, buff );  
   } else  
      perror( "mktime failed" );  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Current time is Fri Apr 25 13:34:07 2003  
  
In 20 days the time will be Thu May 15 13:34:07 2003  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 <xref:System.DateTimeOffset.%23ctor%2A>  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_mkgmtime、_mkgmtime32、_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)
