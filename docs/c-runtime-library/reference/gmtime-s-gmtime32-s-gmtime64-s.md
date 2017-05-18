---
title: "gmtime_s、 _gmtime32_s、 _gmtime64_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _gmtime32_s
- gmtime_s
- _gmtime64_s
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
- _gmtime_s
- gmtime64_s
- gmtime32_s
- _gmtime64_s
- gmtime_s
- _gmtime32_s
dev_langs:
- C++
helpviewer_keywords:
- gmtime_s function
- gmtime32_s function
- time functions
- gmtime64_s function
- _gmtime64_s function
- time structure conversion
- _gmtime_s function
- _gmtime32_s function
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
caps.latest.revision: 29
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e130b125651c29a4ba2607b47b02b95c81468869
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="gmtimes-gmtime32s-gmtime64s"></a>gmtime_s、_gmtime32_s、_gmtime64_s
時刻の値を構造体に変換します。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) で説明されているように、セキュリティが強化されたバージョンの [_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t gmtime_s(  
   struct tm* _tm,  
   const __time_t* time  
);  
errno_t _gmtime32_s(  
   struct tm* _tm,  
   const __time32_t* time  
);  
errno_t _gmtime64_s(  
   struct tm* _tm,  
   const __time64_t* time   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_tm`  
 `tm` 構造体へのポインター。 返された構造体の各フィールドには、`timer` 引数を現地時刻ではなく UTC で評価した値が格納されています。  
  
 `time`  
 格納されている時刻へのポインター。 時刻は、世界協定時刻 (UTC: Coordinated Universal Time) の 1970 年 1 月 1 日の深夜 00:00:00 から経過した時間 (秒単位) を表します。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは Errno.h で定義されます。これらのエラーの一覧については、[errno](../../c-runtime-library/errno-constants.md) をご覧ください。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`_tm`|`time`|リターン|`_tm` の値|  
|-----------|------------|------------|--------------------|  
|`NULL`|任意|`EINVAL`|変更されません。|  
|`NULL` ではない (有効なメモリを指す)|`NULL`|`EINVAL`|すべてのフィールドが-1 に設定されます。|  
|`NULL` ではない|< 0|`EINVAL`|すべてのフィールドが-1 に設定されます。|  
  
 最初の 2 つのエラーの場合は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」 (パラメーターの検証) に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_gmtime32_s` 関数は、`time` 値を展開して、TIME.H に定義された `tm` 型の構造体に保存します。 構造体のアドレスが `_tm` に渡されます。 `time` 値は、通常は `time` 関数の呼び出しにより取得されます。  
  
> [!NOTE]
>  対象の環境によって、夏時間が有効かどうか判断されます。 C ランタイム ライブラリでは、アメリカ合衆国の規則を前提に夏時間を計算します。  
  
 構造体の各フィールドは `int` 型で、次の表のとおりです。  
  
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
  
 `__time64_t` 構造体を使用する `_gmtime64_s` は、UTC の 3000 年 12 月 31 日の 23 時 59 分 59 秒までの日付を表すことができます。それに対して、`gmtime32_s` は、UTC の 2038 年 1 月 18 日の 23 時 59 分 59 秒までしか表すことができません。 これらの関数の日付範囲の下限は、どちらも 1970 年 1 月 1 日の午前 0 時です。  
  
 `gmtime_s` は `_gmtime64_s` を求めるインライン関数であり、`time_t` は `__time64_t` と等価です。 コンパイラが `time_t` を古い 32 ビットの `time_t` として解釈するよう強制する必要がある場合には、`_USE_32BIT_TIME_T` を定義します。 これにより、`gmtime_s` は `_gmtime32_s`にインライン化されます。 ただし、この方法は推奨されません。2038 年 1 月 18 日以降にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`gmtime_s`|\<time.h>|  
|`_gmtime32_s`|\<time.h>|  
|`_gmtime64_s`|\<time.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_gmtime64_s.c  
// This program uses _gmtime64_s to convert a 64-bit  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime_s to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm newtime;  
   __int64 ltime;  
   char buf[26];  
   errno_t err;  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:   
   err = _gmtime64_s( &newtime, &ltime );  
   if (err)  
   {  
      printf("Invalid Argument to _gmtime64_s.");  
   }  
  
   // Convert to an ASCII representation   
   err = asctime_s(buf, 26, &newtime);  
   if (err)  
   {  
      printf("Invalid Argument to asctime_s.");  
   }  
  
   printf( "Coordinated universal time is %s\n",   
           buf );  
}  
```  
  
```Output  
Coordinated universal time is Fri Apr 25 20:12:33 2003  
```  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [_mkgmtime、_mkgmtime32、_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime、_mktime32、_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)
