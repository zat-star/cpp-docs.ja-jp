---
title: "gmtime、_gmtime32、_gmtime64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
dev_langs: C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 78213f97021ad1e7c89d5dfde6c1cea8b6e12a7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime、_gmtime32、_gmtime64
時刻の値を構造体に変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
struct tm *gmtime(   
   const time_t *timer   
);  
struct tm *_gmtime32(   
   const __time32_t *timer   
);  
struct tm *_gmtime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `timer`  
 格納されている時刻へのポインター。 時刻は、世界協定時刻 (UTC: Coordinated Universal Time) の 1970 年 1 月 1 日の深夜 00:00:00 から経過した時間 (秒単位) を表します。  
  
## <a name="return-value"></a>戻り値  
 型 [tm](../../c-runtime-library/standard-types.md) 構造体へのポインター。 返された構造体の各フィールドには、`timer` 引数を現地時刻ではなく UTC で評価した値が格納されています。 構造体の各フィールドは `int` 型で、次のとおりです:  
  
 `tm_sec`  
 秒 (0 ~ 59)。  
  
 `tm_min`  
 分 (0 ~ 59)。  
  
 `tm_hour`  
 午前 0 時からの経過時間 (0 ~ 23)。  
  
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
 `gmtime` では常に 0。  
  
 32 ビット バージョンおよび 64 ビット バージョンの `gmtime`、`mktime`、`mkgmtime`、`localtime` の各関数はすべて、1 スレッドあたり共通の `tm` 構造体を 1 つ使用して変換を行います。 これらの関数を呼び出すたびに、前の呼び出しの結果は破棄されます。 `timer` が 1970 年 1 月 1 日の深夜 0 時よりも前の日付を示している場合、`gmtime` は `NULL` を返します。 エラーの戻り値はありません。  
  
 `_gmtime64` 構造体を使用する `__time64_t` は、UTC の 3000 年 12 月 31 日の 23 時 59 分 59 秒までの日付を表すことができます。それに対して、`_gmtime32` は、UTC の 2038 年 1 月 18 日の 23 時 59 分 59 秒までしか表すことができません。 これらの関数の日付範囲の下限は、どちらも 1970 年 1 月 1 日の午前 0 時です。  
  
 `gmtime` は `_gmtime64` に評価されるインライン関数であり、`time_t` は `__time64_t` が定義されている場合を除き `_USE_32BIT_TIME_T` と等価です。 コンパイラに `time_t` を従来の 32 ビットの `time_t` として解釈させる必要がある場合は、`_USE_32BIT_TIME_T` を定義できますが、そのためには `gmtime` を `_gmtime32` にインライン展開し、`time_t` を `__time32_t` として定義します。 この方法は使用しないことをお勧めします。これは 64 ビット プラットフォームでは使用できず、また 2038 年 1 月 18 日以降はアプリケーションでエラーが発生する可能性があるためです。  
  
 これらの関数では、パラメーターの検証が行われます。 `timer` が null ポインターの場合またはタイマー値が負の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="remarks"></a>コメント  
 `_gmtime32` 関数は、`timer` 値を展開して、TIME.H に定義され、静的に割り当てられた `tm` 型の構造体に保存します。 `timer` 値は、通常は `time` 関数の呼び出しにより取得されます。  
  
> [!NOTE]
>  ほとんどの場合は、対象の環境で夏時間が有効かどうかを確認してください。 C ランタイム ライブラリでは、夏時間 (DST) の計算にアメリカ合衆国の規則が使用されていることを前提とします。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`gmtime`|\<time.h>|  
|`_gmtime32`|\<time.h>|  
|`_gmtime64`|\<time.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```C  
// crt_gmtime.c  
// compile with: /W3  
// This program uses _gmtime64 to convert a long-  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm *newtime;  
   __int64 ltime;  
   char buff[80];  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:  
   newtime = _gmtime64( &ltime ); // C4996  
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s  
   asctime_s( buff, sizeof(buff), newtime );  
   printf( "Coordinated universal time is %s\n", buff );  
}  
```  
  
```Output  
Coordinated universal time is Tue Feb 12 23:11:31 2002  
```  
  
## <a name="see-also"></a>参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_mkgmtime、_mkgmtime32、_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime、_mktime32、_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)