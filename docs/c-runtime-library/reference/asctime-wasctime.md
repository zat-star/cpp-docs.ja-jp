---
title: "asctime、_wasctime |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wasctime
- asctime
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
- _tasctime
- asctime
- _wasctime
dev_langs:
- C++
helpviewer_keywords:
- asctime function
- tasctime function
- wasctime function
- _tasctime function
- _wasctime function
- time structure conversion
- time, converting
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c89b43613e1eb82eb35876ea733e13c5d2995352
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="asctime-wasctime"></a>asctime、_wasctime
`tm` 時間構造体を文字列に変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
char *asctime(   
   const struct tm *timeptr   
);  
wchar_t *_wasctime(   
   const struct tm *timeptr   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `timeptr`  
 時刻/日付の構造体。  
  
## <a name="return-value"></a>戻り値  
 `asctime` は文字列結果へのポインターを返し、`_wasctime` はワイド文字結果へのポインターを返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 これらの関数のセキュリティを強化したバージョンを使用できます。「[asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)」を参照してください。  
  
 `asctime` 関数は、構造体として格納されている時間を文字列に変換します。 `timeptr` 値は通常、TIME.H で定義された `tm` 構造体へのポインターを返す、`gmtime` または `localtime` への呼び出しから取得されます。  
  
|timeptr メンバー|[値]|  
|--------------------|-----------|  
|`tm_hour`|午前 0 時 (0 ~ 23) 以降の時間|  
|`tm_isdst`|夏時間が有効な場合は正、夏時間が無効な場合は 0、夏時間かどうかが不明な場合は負。 C ランタイム ライブラリでは、アメリカ合衆国の規則を前提に夏時間 (DST) を計算します。|  
|`tm_mday`|(1 ~ 31) の月の日|  
|`tm_min`|分 (0 ~ 59)|  
|`tm_mon`|月 (0 ~ 11 です。年 1 月 = 0)|  
|`tm_sec`|秒 (0 ~ 59)|  
|`tm_wday`|曜日 (0 ~ 6 です。日曜日 = 0)|  
|`tm_yday`|年 (0 ~ 365; の日付1 月 1 日 = 0)|  
|`tm_year`|年 (実際の西暦から 1900 を引いた数)|  
  
 変換された文字列も、ローカル タイム ゾーンの設定に従って調整されます。 ローカル タイムの設定の詳細については、[time](../../c-runtime-library/reference/time-time32-time64.md)、[_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)、および [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) の関数を参照してください。また、タイム ゾーン環境とグローバル変数の定義の詳細については、[_tzset](../../c-runtime-library/reference/tzset.md) 関数を参照してください。  
  
 `asctime` によって生成される文字列には、26 文字が含まれ、`Wed Jan 02 02:03:55 1980\n\0` の形式となります。 24 時間制が使用されます。 すべてのフィールドには一定の幅があります。 文字列の最後の 2 つの位置には、改行文字と null 文字が入ります。 `asctime` は、静的に割り当てられた単一のバッファーを使って戻り値の文字列を保持します。 この関数を呼び出すたびに、前の呼び出しの結果は破棄されます。  
  
 `_wasctime` 関数は、`asctime` 関数のワイド文字バージョンです。 それ以外では、`_wasctime` と `asctime` の動作は同じです。  
  
 これらの関数では、パラメーターの検証が行われます。 `timeptr` が null ポインターの場合、または範囲外の値が含まれる場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
### <a name="generic-text-routine-mapping"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tasctime`|`asctime`|`asctime`|`_wasctime`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`asctime`|\<time.h>|  
|`_wasctime`|\<time.h> または \<wchar.h>|  
  
## <a name="example"></a>例  
 このプログラムはシステム時刻を長整数 `aclock` で配置し、それを構造体 `newtime` に変換してから、`asctime` 関数を使用して出力用の文字列形式に変換します。  
  
```  
// crt_asctime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
    struct tm   *newTime;  
    time_t      szClock;  
  
    // Get time in seconds  
    time( &szClock );  
  
    // Convert time to struct tm form   
    newTime = localtime( &szClock );  
  
    // Print local time as a string.  
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996  
    // Note: asctime is deprecated; consider using asctime_s instead  
}  
```  
  
```Output  
Current date and time: Sun Feb 03 11:38:58 2002  
```  
  
## <a name="see-also"></a>参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)   
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)