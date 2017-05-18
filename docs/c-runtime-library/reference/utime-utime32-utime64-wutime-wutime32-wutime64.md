---
title: "_utime、_utime32、_utime64、_wutime、_wutime32、_wutime64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _utime64
- _utime
- _wutime
- _wutime64
- _wutime32
- _utime32
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
- _tutime
- _utime64
- wutime
- utime32
- wutime64
- _utime
- wutime32
- _wutime
- utime
- utime64
- _wutime64
- _utime32
- _tutime64
- _wutime32
dev_langs:
- C++
helpviewer_keywords:
- tutime function
- utime32 function
- utime64 function
- _utime function
- _tutime32 function
- time [C++], file modification
- wutime function
- _wutime function
- _wutime32 function
- _tutime64 function
- _tutime function
- files [C++], modification time
- _wutime64 function
- _utime32 function
- utime function
- _utime64 function
- wutime64 function
- wutime32 function
- tutime64 function
- tutime32 function
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
caps.latest.revision: 16
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
ms.openlocfilehash: 80836179c63da2f62384abd07fe2a4970d9bce55
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="utime-utime32-utime64-wutime-wutime32-wutime64"></a>_utime、_utime32、_utime64、_wutime、_wutime32、_wutime64
ファイルの変更時刻を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _utime(  
   const char *filename,  
   struct _utimbuf *times   
);  
int _utime32(  
   const char *filename,  
   struct __utimbuf32 *times   
);  
int _utime64(  
   const char *filename,  
   struct __utimbuf64 *times   
);  
int _wutime(  
   const wchar_t *filename,  
   struct _utimbuf *times   
);  
int _wutime32(  
   const wchar_t *filename,  
   struct __utimbuf32 *times   
);  
int _wutime64(  
   const wchar_t *filename,  
   struct __utimbuf64 *times   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `filename`  
 パスまたはファイル名を含む文字列へのポインター。  
  
 `times`  
 格納されている時刻値へのポインター。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、ファイルの変更時刻が変更されると、0 を返します。 戻り値-1 はエラーを示します。 無効なパラメーターが渡された場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は -1 を返し、`errno` を次のいずれかの値に設定します。  
  
 `EACCES`  
 パスにディレクトリまたは読み取り専用ファイルが指定されている  
  
 `EINVAL`  
 無効な `times` 引数  
  
 `EMFILE`  
 開いているファイルが多すぎる (変更時刻を変更するにはファイルを開く必要があります)  
  
 `ENOENT`  
 パスまたはファイル名が見つからない  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 変更日が 1970 年 1 月 1 日午前 0 時以降で、使用する関数の終了日より前の場合、ファイルの日付を変更できます。 `_utime` と `_wutime` は 64 ビットの時刻値を使用するため、終了日は UTC の 3000 年 12 月 31 日 23 時 59 分 59 秒になります。 以前の動作を強制するよう `_USE_32BIT_TIME_T` が定義されている場合、終了日は UTC の 2038 年 1 月 18 日 23 時 59 分 59 秒になります。 `_utime32` または `_wutime32` は、`_USE_32BIT_TIME_T` の定義内容に関係なく 32 ビットの時刻型を使用し、常に早いほうの終了日を使用します。 `_utime64` または `_wutime64` は常に 64 ビットの時刻型を使用するため、これらの関数では遅いほうの終了日がサポートされます。  
  
## <a name="remarks"></a>コメント  
 `_utime` 関数は、`filename` *によって指定されたファイルの変更時刻を設定します。* プロセスは、時刻を変更するために、ファイルに対して書き込みアクセス権が必要です。 Windows オペレーティング システムでは、`_utimbuf` 構造体でアクセス時刻および変更時刻を変更できます。 `times` が `NULL` ポインターである場合、変更時刻は現在の現地時刻に設定されます。 それ以外の場合、`times` は、SYS\UTIME.H で定義されている型 `_utimbuf` の構造体を指す必要があります。  
  
 `_utimbuf` 構造体は、`_utime` でファイル変更日を変更するために使用する、ファイルへのアクセス時刻および変更時刻を格納します。 構造体には、いずれも型 `time_t` である次のフィールドがあります。  
  
 `actime`  
 ファイルへのアクセス時刻  
  
 `modtime`  
 ファイルの変更時刻  
  
 特定のバージョンの `_utimbuf` 構造体 (`_utimebuf32` と `__utimbuf64`) は、32 ビット バージョンと 64 ビット バージョンの時刻型を使用して定義されます。 これらは、この関数の 32 ビットおよび 64 ビットの特定バージョンで使用されます。 `_utimbuf` 自体は、`_USE_32BIT_TIME_T` が定義されていない場合、既定で 64 ビットの時刻型を使用します。  
  
 `_utime` は `_futime` と同じですが、`_utime` の引数 `filename` が開いているファイルのファイル記述子ではなくファイル名またはファイルへのパスである点が異なります。  
  
 `_wutime` 関数は、`_utime` 関数のワイド文字バージョンです。`filename` 関数の引数 `_wutime` は、ワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tutime`|`_utime`|`_utime`|`_wutime`|  
|`_tutime32`|`_utime32`|`_utime32`|`_wutime32`|  
|`_tutime64`|`_utime64`|`_utime64`|`_wutime64`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|-------------|----------------------|----------------------|  
|`_utime`、`_utime32`、`_utime64`|\<sys/utime.h>|\<errno.h>|  
|`_utime64`|\<sys/utime.h>|\<errno.h>|  
|`_wutime`|\<utime.h> または \<wchar.h>|\<errno.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 このプログラムは `_utime` を使用して、ファイル変更時刻を現在の時刻に設定します。  
  
```  
// crt_utime.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <sys/types.h>  
#include <sys/utime.h>  
#include <time.h>  
  
int main( void )  
{  
   struct tm tma = {0}, tmm = {0};  
   struct _utimbuf ut;  
  
   // Fill out the accessed time structure  
   tma.tm_hour = 12;  
   tma.tm_isdst = 0;  
   tma.tm_mday = 15;  
   tma.tm_min = 0;  
   tma.tm_mon = 0;  
   tma.tm_sec = 0;  
   tma.tm_year = 103;  
  
   // Fill out the modified time structure  
   tmm.tm_hour = 12;  
   tmm.tm_isdst = 0;  
   tmm.tm_mday = 15;  
   tmm.tm_min = 0;  
   tmm.tm_mon = 0;  
   tmm.tm_sec = 0;  
   tmm.tm_year = 102;  
  
   // Convert tm to time_t  
   ut.actime = mktime(&tma);  
   ut.modtime = mktime(&tmm);  
  
   // Show file time before and after  
   system( "dir crt_utime.c" );  
   if( _utime( "crt_utime.c", &ut ) == -1 )  
      perror( "_utime failed\n" );  
   else  
      printf( "File time modified\n" );  
   system( "dir crt_utime.c" );  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/09/2003  05:38 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
File time modified  
 Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/15/2002  12:00 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
```  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [_futime、_futime32、_futime64](../../c-runtime-library/reference/futime-futime32-futime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_stat、_wstat 関数](../../c-runtime-library/reference/stat-functions.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)
