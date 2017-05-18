---
title: "ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64 | Microsoft Doc"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
dev_langs:
- C++
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f3d756cec6d9482cfabcbc2a336cbf5d6381a97a
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64
時刻値を文字列に変換し、ローカルの時間帯設定に合わせて調整します。 これらの関数には、より安全なバージョンがあります。「[ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `timer`  
 格納されている時刻へのポインター。  
  
## <a name="return-value"></a>戻り値  
 文字列結果へのポインター。 次の場合、`NULL` が返されます。  
  
-   `time` が 1970 年 1 月 1 日の深夜 0 時 (協定世界時) よりも前の日付を示している場合。  
  
-   `_ctime32` または `_wctime32` と `time` が 2038 年 1 月 18 日の 23:59:59 時 (協定世界時) よりも後の日付を示している場合。  
  
-   `_ctime64` または `_wctime64` と `time` が 3000 年 12 月 31 日の 23:59:59 時 (協定世界時) よりも後の日付を示している場合。  
  
 `ctime` は `_ctime64` を求めるインライン関数であり、`time_t` は `__time64_t` と等価です。 コンパイラが `time_t` を古い 32 ビットの `time_t` として解釈するよう強制する必要がある場合には、`_USE_32BIT_TIME_T` を定義します。 これにより、`ctime` の値は `_ctime32` になります。 この方法はお勧めしません。2038 年 1 月 18 日より後にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。  
  
## <a name="remarks"></a>コメント  
 `ctime` 関数は、[time_t](../../c-runtime-library/standard-types.md) 値として格納されている時間を文字列に変換します。 `timer` 値は通常、協定世界時刻 (UTC) の 1970 年 1 月 1 日の真夜中 (00:00:00) 以降の経過時間を返す [time](../../c-runtime-library/reference/time-time32-time64.md) を呼び出すことで取得されます。 戻り値には厳密に 26 文字が含まれ、次の形式になります。  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24 時間制が使用されます。 すべてのフィールドには一定の幅があります。 文字列の最後の 2 つの位置には、改行文字 ('\n') と null 文字 ('\0') が入ります。  
  
 変換された文字列も、ローカル タイム ゾーンの設定に従って調整されます。 ローカル タイムの設定については、`time`、[_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)、[localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 関数を参照してください。タイム ゾーン環境とグローバル変数の定義については、[_tzset](../../c-runtime-library/reference/tzset.md) 関数を参照してください。  
  
 `ctime` を呼び出すと、`gmtime` 関数と `localtime` 関数により使用される、静的に割り当てられた 1 つのバッファーが変更されます。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。 `ctime` は、`asctime` 関数と静的バッファーを共有します。 そのため、`ctime` を呼び出すと、`asctime`、`localtime`、または `gmtime` を以前に呼び出した結果が破棄されます。  
  
 `_wctime` と `_wctime64` は `ctime` と `_ctime64` のワイド文字バージョンです。ワイド文字列のポインターを返します。 それ以外では、`_ctime64`、`_wctime`、`_wctime64` の動作は `ctime` と同じです。  
  
 これらの関数では、パラメーターの検証が行われます。 `timer` が Null ポインターの場合またはタイマー値が負の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`ctime`|\<time.h>|  
|`_ctime32`|\<time.h>|  
|`_ctime64`|\<time.h>|  
|`_wctime`|\<time.h> または \<wchar.h>|  
|`_wctime32`|\<time.h> または \<wchar.h>|  
|`_wctime64`|\<time.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
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
The time is Wed Feb 13 16:04:43 2002  
```  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)
