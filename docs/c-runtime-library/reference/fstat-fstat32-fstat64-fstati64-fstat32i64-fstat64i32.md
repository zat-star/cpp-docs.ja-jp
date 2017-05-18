---
title: "_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fstat32
- _fstat64
- _fstati64
- _fstat
- _fstat64i32
- _fstat32i64
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstat32i64
- fstat
- fstat64i32
- _fstat64
- _fstati64
- fstat64
- _fstat32
- fstat32i64
- fstati64
- _fstat
- fstat32
- _fstat64i32
dev_langs:
- C++
helpviewer_keywords:
- _fstat64 function
- fstati64 function
- _fstat64i32 function
- _fstat32i64 function
- _fstat32 function
- file information
- fstat64i32 function
- fstat32 function
- fstat function
- fstat64 function
- _fstat function
- _fstati64 function
- fstat32i64 function
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
caps.latest.revision: 23
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
ms.openlocfilehash: 4bf1e3ad35fb03891f9c861255919752d0403d70
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32"></a>_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32
開いているファイルに関する情報を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
int _fstat(   
   int fd,  
   struct _stat *buffer   
);  
int _fstat32(   
   int fd,  
   struct __stat32 *buffer   
);  
int _fstat64(   
   int fd,  
   struct __stat64 *buffer   
);  
int _fstati64(   
   int fd,  
   struct _stati64 *buffer   
);  
int _fstat32i64(   
   int fd,  
   struct _stat32i64 *buffer   
);  
int _fstat64i32(   
   int fd,  
   struct _stat64i32 *buffer   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 開いているファイルのファイル記述子。  
  
 `buffer`  
 結果を格納する構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 ファイルのステータス情報が取得されると、0 を返します。 戻り値-1 はエラーを示します。 ファイル記述子が無効な場合または `buffer` が `NULL` である場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、無効なファイル記述子の場合は `errno` が `EBADF` に設定され、`buffer` が `NULL` である場合は、`EINVAL` に設定されます。  
  
## <a name="remarks"></a>コメント  
 `_fstat` 関数は、 `fd` に関連付けられている開いているファイルに関する情報を取得し、`buffer` によって示される構造体にそれを格納します。 `_stat` 構造体 (SYS\Stat.h で定義される) には、次のフィールドが含まれています。  
  
 `st_atime`  
 ファイルの最後のアクセスの時間。  
  
 `st_ctime`  
 ファイルの作成の時間。  
  
 `st_dev`  
 デバイスの場合は `fd`、それ以外の場合は 0 です。  
  
 `st_mode`  
 ファイル モード情報のビット マスク。 `fd` がデバイスを参照している場合は、`_S_IFCHR` ビットが設定されます。 `fd` が通常のファイルを参照している場合は、`_S_IFREG` ビットが設定されます。 読み取り/書き込みのビットは、ファイルのアクセス許可モードに応じて設定されます。 `_S_IFCHR` およびその他の定数は、SYS\Stat.h で定義されます。  
  
 `st_mtime`  
 ファイルの最終変更時刻。  
  
 `st_nlink`  
 非 NTFS ファイル システムでは常に 1 です。  
  
 `st_rdev`  
 デバイスの場合は `fd`、それ以外の場合は 0 です。  
  
 `st_size`  
 ファイルのサイズ (バイト単位)。  
  
 `fd` がデバイスを鑑賞している場合、`st_atime`、`st_ctime`、`st_mtime`、および `st_size` フィールドには意味がありません。  
  
 Stat.h は Types.h で定義される [_dev_t](../../c-runtime-library/standard-types.md) 型を使用するため、コードで Stat.h の前に Types.h を組み込む必要があります。  
  
 `__stat64` 構造体を使用する `_fstat64` は、UTC の 3000 年 12 月 31 日の 23 時 59 分 59 秒までのファイル作成日付を表すことができます。それに対して、他の関数は、UTC の 2038 年 1 月 18 日の 23 時 59 分 59 秒までしか表すことができません。 これらの関数の日付範囲の下限は、いずれも 1970 年 1 月 1 日の午前 0 時です。  
  
 これらの関数のバリエーションは、32 ビットや 64 ビットの時刻型と、32 ビットや 64 ビットのファイル長をサポートします。 最初の数字のサフィックス (`32` または `64`) は、使用される時刻型のサイズを示します。2 番目のサフィックスは `i32` または `i64`で、ファイル サイズが 32 ビットの整数として表されるか、それとも 64 ビットの整数として表されるかを示します。  
  
 `_fstat` は `_fstat64i32` と同等で、`struct _stat` には 64 ビットの時刻が含まれます。 これは、 `_USE_32BIT_TIME_T` が定義されていない場合に当てはまります。定義されている場合には、古い動作が有効になります。 `_fstat` は 32 ビットの時刻を使用します。 `struct _stat` には 32 ビットの時刻が含まれます。 同じことが `_fstati64`にも当てはまります。  
  
### <a name="time-type-and-file-length-type-variations-of-stat"></a>_stat の時刻型とファイル長型のバリエーション  
  
|関数|_USE_32BIT_TIME_T が定義されているか|時刻型|ファイル長型|  
|---------------|------------------------------------|---------------|----------------------|  
|`_fstat`|未定義|64 ビット|32 ビット|  
|`_fstat`|定義済み|32 ビット|32 ビット|  
|`_fstat32`|マクロ定義の影響を受けない|32 ビット|32 ビット|  
|`_fstat64`|マクロ定義の影響を受けない|64 ビット|64 ビット|  
|`_fstati64`|未定義|64 ビット|64 ビット|  
|`_fstati64`|定義済み|32 ビット|64 ビット|  
|`_fstat32i64`|マクロ定義の影響を受けない|32 ビット|64 ビット|  
|`_fstat64i32`|マクロ定義の影響を受けない|64 ビット|32 ビット|  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_fstat`|\<sys/stat.h> と \<sys/types.h>|  
|`_fstat32`|\<sys/stat.h> と \<sys/types.h>|  
|`_fstat64`|\<sys/stat.h> と \<sys/types.h>|  
|`_fstati64`|\<sys/stat.h> と \<sys/types.h>|  
|`_fstat32i64`|\<sys/stat.h> と \<sys/types.h>|  
|`_fstat64i32`|\<sys/stat.h> と \<sys/types.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_fstat.c  
// This program uses _fstat to report  
// the size of a file named F_STAT.OUT.  
  
#include <io.h>  
#include <fcntl.h>  
#include <time.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <errno.h>  
#include <share.h>  
  
int main( void )  
{  
   struct _stat buf;  
   int fd, result;  
   char buffer[] = "A line to output";  
   char timebuf[26];  
   errno_t err;  
  
   _sopen_s( &fd,  
             "f_stat.out",  
             _O_CREAT | _O_WRONLY | _O_TRUNC,  
             _SH_DENYNO,  
             _S_IREAD | _S_IWRITE );  
   if( fd != -1 )  
      _write( fd, buffer, strlen( buffer ) );  
  
   // Get data associated with "fd":   
   result = _fstat( fd, &buf );  
  
   // Check if statistics are valid:   
   if( result != 0 )  
   {  
      if (errno == EBADF)  
        printf( "Bad file descriptor.\n" );  
      else if (errno == EINVAL)  
        printf( "Invalid argument to _fstat.\n" );  
   }  
   else  
   {  
      printf( "File size     : %ld\n", buf.st_size );  
      err = ctime_s(timebuf, 26, &buf.st_mtime);  
      if (err)  
      {  
         printf("Invalid argument to ctime_s.");  
         exit(1);  
      }  
      printf( "Time modified : %s", timebuf );  
   }  
   _close( fd );  
}  
```  
  
```Output  
File size     : 16  
Time modified : Wed May 07 15:25:11 2003  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_access、_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod、_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_filelength、_filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [_stat、_wstat 関数](../../c-runtime-library/reference/stat-functions.md)
