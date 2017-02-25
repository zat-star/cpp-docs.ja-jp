---
title: "_utime、_utime32、_utime64、_wutime、_wutime32、_wutime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_utime64"
  - "_utime"
  - "_wutime"
  - "_wutime64"
  - "_wutime32"
  - "_utime32"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tutime"
  - "_utime64"
  - "wutime"
  - "utime32"
  - "wutime64"
  - "_utime"
  - "wutime32"
  - "_wutime"
  - "utime"
  - "utime64"
  - "_wutime64"
  - "_utime32"
  - "_tutime64"
  - "_wutime32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tutime 関数"
  - "utime32 関数"
  - "utime64 関数"
  - "_utime 関数"
  - "_tutime32 関数"
  - "時刻 [C++]、ファイルの変更"
  - "wutime 関数"
  - "_wutime 関数"
  - "_wutime32 関数"
  - "_tutime64 関数"
  - "_tutime 関数"
  - "ファイル [C++]、変更時刻"
  - "_wutime64 関数"
  - "_utime32 関数"
  - "utime 関数"
  - "_utime64 関数"
  - "wutime64 関数"
  - "wutime32 関数"
  - "tutime64 関数"
  - "tutime32 関数"
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _utime、_utime32、_utime64、_wutime、_wutime32、_wutime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルの変更時刻を設定します。  
  
## 構文  
  
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
  
#### パラメーター  
 `filename`  
 パスまたはファイル名を表す文字列へのポインター。  
  
 `times`  
 格納されている時刻値へのポインター。  
  
## 戻り値  
 これらの各関数は、ファイルの変更の時刻が変更された場合で、0 を返します。 戻り値 \-1 はエラーを示します。 無効なパラメーターが渡された場合、無効なパラメーター ハンドラーが呼び出される」の説明に従って [パラメーターの検証](../../c-runtime-library/parameter-validation.md)します。 実行の継続が許可された場合、これらの関数は\-1 を返しますと `errno` は、次の値のいずれかに設定します。  
  
 `EACCES`  
 パスは、ディレクトリまたは読み取り専用ファイルを指定します。  
  
 `EINVAL`  
 無効な `times` 引数  
  
 `EMFILE`  
 開いているファイルが多すぎます \(その変更時刻を変更するのには、ファイルを開く必要があります\)  
  
 `ENOENT`  
 パスまたはファイル名が見つかりません。  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 変更日が 1970 年 1 月 1 日午前 0 時以降後、および使用する関数の終了日より前に、の場合、ファイルの日付を変更できます。`_utime``_wutime` 終了日が UTC の 3000 年 12 月 31 日 23時 59分: 59 秒であるため、64 ビットの時刻の値を使用します。 場合 `_USE_32BIT_TIME_T` が定義されている、終了日の 23時 59分: 59 2038 年 1 月 18 日 \(utc\) が以前の動作を強制的にします。`_utime32` または `_wutime32` かどうかに関係なく 32 ビット時の型を使用して `_USE_32BIT_TIME_T` を定義すると、常に、以前の終了日。`_utime64` または `_wutime64` ため、これらの関数は、以降の終了日を常にサポート、64 ビット時の型を常に使用します。  
  
## 解説  
 `_utime` 関数によって指定されたファイルの修正時間を設定する `filename`*.*プロセスは、時間を変更するために、ファイルに書き込みアクセス権が必要です。 Windows オペレーティング システムでは、アクセス時間との変更時刻を変更できます、 `_utimbuf` 構造体。 場合 `times` は、 `NULL` ポインター、最終更新日は現在の現地時刻に設定します。 それ以外の場合、 `times` 型の構造体をポイントしなければなりません `_utimbuf`, に定義されている。H.  
  
 `_utimbuf` 構造体で使用されるファイル アクセス、および変更時刻を格納する `_utime` ファイル変更日を変更します。 構造体には、型のどちらも、次のフィールド `time_t`:  
  
 `actime`  
 ファイルのアクセス時刻  
  
 `modtime`  
 ファイルの変更時刻  
  
 特定のバージョンの `_utimbuf` 構造 \(`_utimebuf32` と `__utimbuf64`\) は時刻型の 32 ビットおよび 64 ビット バージョンを使用して定義します。 これらは、この関数の 32 ビットおよび 64 ビット特定のバージョンで使用されます。`_utimbuf` 64 ビットの時刻型を使用してしない限り、既定ではそれ自体 `_USE_32BIT_TIME_T` が定義されています。  
  
 `_utime` 同じ `_futime` する点を除いて、 `filename` の引数 `_utime` は、ファイル名または開いているファイルのファイル記述子ではなく、ファイルへのパス。  
  
 `_wutime` 関数は、`_utime` 関数のワイド文字バージョンです。`filename` 関数の引数 `_wutime` は、ワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tutime`|`_utime`|`_utime`|`_wutime`|  
|`_tutime32`|`_utime32`|`_utime32`|`_wutime32`|  
|`_tutime64`|`_utime64`|`_utime64`|`_wutime64`|  
  
## 必要条件  
  
|ルーチン|必要なヘッダー|省略可能なヘッダー|  
|----------|-------------|---------------|  
|`_utime`、`_utime32`、`_utime64`|\< sys\/utime.h \>|\<errno.h\>|  
|`_utime64`|\< sys\/utime.h \>|\<errno.h\>|  
|`_wutime`|\< utime.h \> または \< wchar.h \>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 このプログラムは `_utime` ファイル変更時刻を現在の時刻に設定します。  
  
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
  
## 出力例  
  
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
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、\_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime、\_ctime32、\_ctime64、\_wctime、\_wctime32、\_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_fstat、\_fstat32、\_fstat64、\_fstati64、\_fstat32i64、\_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [\_futime、\_futime32、\_futime64](../../c-runtime-library/reference/futime-futime32-futime64.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、\_localtime32、\_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_stat、\_wstat 関数](../../c-runtime-library/reference/stat-functions.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)