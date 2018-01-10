---
title: "_stat、_stat32、_stat64、_stati64、_stat32i64、_stat64i32、_wstat、_wstat32、_wstat64、_wstati64、_wstat32i64、_wstat64i32 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wstat64
- _stati64
- _stat32
- _stat32i64
- _stat
- _wstati64
- _wstat32
- _wstat64i32
- _wstat
- _stat64
- _stat64i32
- _wstat32i64
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
- tstat32
- tstat
- _tstat64i32
- tstati64
- _wstat64
- _wstat32
- wstati64
- tstat64
- _stati64
- _wstat
- wstat64i32
- stat32i64
- tstat32i64
- _tstat
- _wstati64
- _tstati64
- _wstat32i64
- wstat32
- _wstat64i32
- _stat
- _tstat32
- stat64i32
- wstat64
- stat
- _stat32i64
- _stat32
- stati64
- wstat
- _stat64i32
- stat32
- _tstat32i64
- tstat64i32
- _tstat64
- _stat64
- stat/_stat
- stat/_stat32
- stat/_stat64
- stat/_stati64
- stat/_stat32i64
- stat/_stat64i32
- stat/_wstat
- stat/_wstat32
- stat/_wstat64
- stat/_wstati64
- stat/_wstat32i64
- stat/_wstat64i32
dev_langs: C++
helpviewer_keywords:
- files [C++], status information
- _stat function
- _wstat function
- _stat64i32 function
- tstat function
- _tstat64i32 function
- _stati64 function
- _stat64 function
- tstati64 function
- wstati64 function
- wstat64 function
- _wstat64i32 function
- _tstat32i64 function
- _stat32i64 function
- stat function
- status of files
- _tstat32 function
- tstat64 function
- _wstat64 function
- _tstat function
- _stat32 function
- wstat function
- _wstat32i64 function
- _tstati64 function
- _wstat32 function
- stat64 function
- stati64 function
- _wstati64 function
- _tstat64 function
- files [C++], getting status information
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed4a232cc5d563a724adf29500e70aa28cf36432
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stat-stat32-stat64-stati64-stat32i64-stat64i32-wstat-wstat32-wstat64-wstati64-wstat32i64-wstat64i32"></a>_stat、_stat32、_stat64、_stati64、_stat32i64、_stat64i32、_wstat、_wstat32、_wstat64、_wstati64、_wstat32i64、_wstat64i32
ファイルのステータス情報を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
int _stat(  
   const char *path,  
   struct _stat *buffer   
);  
int _stat32(  
   const char *path,  
   struct __stat32 *buffer   
);  
int _stat64(  
   const char *path,  
   struct __stat64 *buffer   
);  
int _stati64(  
   const char *path,  
   struct _stati64 *buffer   
);  
int _stat32i64(  
   const char *path,  
   struct _stat32i64 *buffer   
);  
int _stat64i32(  
   const char *path,  
   struct _stat64i32 *buffer   
);  
int _wstat(  
   const wchar_t *path,  
   struct _stat *buffer   
);  
int _wstat32(  
   const wchar_t *path,  
   struct __stat32 *buffer   
);  
int _wstat64(  
   const wchar_t *path,  
   struct __stat64 *buffer   
);  
int _wstati64(  
   const wchar_t *path,  
   struct _stati64 *buffer   
);  
int _wstat32i64(  
   const wchar_t *path,  
   struct _stat32i64 *buffer   
);  
int _wstat64i32(  
   const wchar_t *path,  
   struct _stat64i32 *buffer   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `path`  
 既存のファイルやディレクトリのパスを含む文字列へのポインター。  
  
 `buffer`  
 結果を格納する構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、ファイルのステータス情報が取得されると、0 を返します。 戻り値-1 がいる場合、エラーを示す`errno`に設定されている`ENOENT`、ファイル名またはパスが見つからなかったことを示すです。 `EINVAL` という戻り値は、無効なパラメーターを示します。この場合も `errno` は `EINVAL` に設定されます。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 1970 年 1 月 1 日午前 0 時から 3000 年 12 月 31 日 23:59:59 (UTC) までであれば、ファイルで日付スタンプを表すことができます。ただし、`_stat32` や `_wstat32` を使用していたり、`_USE_32BIT_TIME_T` が定義されている場合を除きます。それらの場合には、2038 年 1 月 18 日 23:59:59 (UTC) までしか日付を表すことができません。  
  
## <a name="remarks"></a>コメント  
 `_stat` 関数は、 `path` によって指定されるファイルやディレクトリに関する情報を取得し、 `buffer`によって示される構造体にそれを格納します。 `_stat` は、現在使用中のマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識し、マルチバイト文字列の引数を適切な方法で自動的に処理します。  
  
 `_wstat` 関数は、 `_stat`関数のワイド文字バージョンです。 `path` 関数の引数 `_wstat` は、ワイド文字列です。 `_wstat` がマルチバイト文字列を処理しない点を除き、 `_stat` と `_wstat` の動作は同じです。  
  
 これらの関数のバリエーションは、32 ビットや 64 ビットの時刻型と、32 ビットや 64 ビットのファイル長をサポートします。 最初の数字のサフィックス (`32` または `64`) は、使用される時刻型のサイズを示します。2 番目のサフィックスは `i32` または `i64`で、ファイル サイズが 32 ビットの整数として表されるか、それとも 64 ビットの整数として表されるかを示します。  
  
 `_stat` は `_stat64i32`と同等で、 `struct _stat` には 64 ビットの時刻が含まれます。 これは、 `_USE_32BIT_TIME_T` が定義されていない場合に当てはまります。定義されている場合には、古い動作が有効になります。 `_stat` は 32 ビットの時刻を使用します。 `struct _stat` には 32 ビットの時刻が含まれます。 同じことが `_stati64`にも当てはまります。  
  
> [!NOTE]
>  `_wstat` は [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] シンボリック リンクでは機能しません。 この場合、 `_wstat` は常に、ファイル サイズとして 0 を報告します。 `_stat` は、シンボリック リンクで正しく機能します。  
  
 この関数は、パラメーターを検証します。 `path` または `buffer` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  
  
### <a name="time-type-and-file-length-type-variations-of-stat"></a>_stat の時刻型とファイル長型のバリエーション  
  
|関数|_USE_32BIT_TIME_T が定義されているか|時刻型|ファイル長型|  
|---------------|------------------------------------|---------------|----------------------|  
|`_stat`, `_wstat`|未定義|64 ビット|32 ビット|  
|`_stat`, `_wstat`|定義済み|32 ビット|32 ビット|  
|`_stat32`, `_wstat32`|マクロ定義の影響を受けない|32 ビット|32 ビット|  
|`_stat64`, `_wstat64`|マクロ定義の影響を受けない|64 ビット|64 ビット|  
|`_stati64`, `_wstati64`|未定義|64 ビット|64 ビット|  
|`_stati64`, `_wstati64`|定義済み|32 ビット|64 ビット|  
|`_stat32i64`, `_wstat32i64`|マクロ定義の影響を受けない|32 ビット|64 ビット|  
|`_stat64i32`, `_wstat64i32`|マクロ定義の影響を受けない|64 ビット|32 ビット|  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstat`|`_stat`|`_stat`|`_wstat`|  
|`_tstat64`|`_stat64`|`_stat64`|`_wstat64`|  
|`_tstati64`|`_stati64`|`_stati64`|`_wstati64`|  
|`_tstat32i64`|`_stat32i64`|`_stat32i64`|`_wstat32i64`|  
|`_tstat64i32`|`_stat64i32`|`_stat64i32`|`_wstat64i32`|  
  
 `_stat` 構造体 (SYS\STAT.H で定義される) には、次のフィールドが含まれています。  
  
 `st_gid`  
 ファイル (UNIX 固有) を所有するグループの数値 ID。Windows システムでは、このフィールドは常に 0 になります。 リダイレクトされたファイルは、Windows ファイルとして分類されます。  
  
 `st_atime`  
 ファイルに最後にアクセスした時刻。 NTFS では有効ですが、FAT 形式のディスク ドライブでは無効です。  
  
 `st_ctime`  
 ファイルの作成時刻。 NTFS では有効ですが、FAT 形式のディスク ドライブでは無効です。  
  
 `st_dev`  
 ファイルを含むディスクのドライブ番号 ( `st_rdev`と同じ)。  
  
 `st_ino`  
 ファイル (UNIX 固有) の情報ノードの数 ( `inode`)。 UNIX ファイル システムでは、 `inode` は、ファイルの日時スタンプ、アクセス許可、コンテンツを記述します。 ファイルが互いにハードリンクされている場合、同じ `inode`を共有します。 `inode`、そして必然的に `st_ino`は、FAT、HPFS、または NTFS ファイル システムでは意味がありません。  
  
 `st_mode`  
 ファイル モード情報のビット マスク。 `_S_IFDIR` がディレクトリを指定する場合、 `path` ビットが設定されます。 `_S_IFREG` が通常のファイルまたはデバイスを指定する場合、 `path` ビットが設定されます。 ユーザーの読み取り/書き込みビットは、ファイルのアクセス許可モードに応じて設定されます。ユーザー実行ビットは、ファイル名の拡張子に応じて設定されます。  
  
 `st_mtime`  
 ファイルの最終変更時刻。  
  
 `st_nlink`  
 非 NTFS ファイル システムでは常に 1 です。  
  
 `st_rdev`  
 ファイルを含むディスクのドライブ番号 ( `st_dev`と同じ)。  
  
 `st_size`  
 ファイルのサイズ (バイト数)。 `i64` サフィックスを持つバリエーションの 64 ビットの整数**。**  
  
 `st_uid`  
 ファイルを所有するユーザーの数値識別子 (UNIX 固有)。 Windows システムでは、このフィールドは常に 0 です。 リダイレクトされたファイルは、Windows ファイルとして分類されます。  
  
 `path` がデバイスを参照する場合、 `st_size`構造体における `st_dev`、各種時刻フィールド、 `st_rdev` 、 `_stat` フィールドには、意味がありません。 STAT.H は TYPES.H で定義されている [_dev_t](../../c-runtime-library/standard-types.md) 型を使用するため、コードで STAT.H の前に TYPES.H を組み込む必要があります。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|  
|-------------|---------------------|----------------------|  
|`_stat`, `_stat32`, `_stat64`, `_stati64`, `_stat32i64`, `_stat64i32`|\<sys/types.h>、その後に \<sys/stat.h>|\<errno.h>|  
|`_wstat`, `_wstat32`, `_wstat64`, `_wstati64`, `_wstat32i64`, `_wstat64i32`|\<sys/types.h>、その後に \<sys/stat.h> または \<wchar.h>|\<errno.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_stat.c  
// This program uses the _stat function to  
// report information about the file named crt_stat.c.  
  
#include <time.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
   struct _stat buf;  
   int result;  
   char timebuf[26];  
   char* filename = "crt_stat.c";  
   errno_t err;  
  
   // Get data associated with "crt_stat.c":   
   result = _stat( filename, &buf );  
  
   // Check if statistics are valid:   
   if( result != 0 )  
   {  
      perror( "Problem getting information" );  
      switch (errno)  
      {  
         case ENOENT:  
           printf("File %s not found.\n", filename);  
           break;  
         case EINVAL:  
           printf("Invalid parameter to _stat.\n");  
           break;  
         default:  
           /* Should never be reached. */  
           printf("Unexpected error in _stat.\n");  
      }  
   }  
   else  
   {  
      // Output some of the statistics:   
      printf( "File size     : %ld\n", buf.st_size );  
      printf( "Drive         : %c:\n", buf.st_dev + 'A' );  
      err = ctime_s(timebuf, 26, &buf.st_mtime);  
      if (err)  
      {  
         printf("Invalid arguments to ctime_s.");  
         exit(1);  
      }  
      printf( "Time modified : %s", timebuf );  
   }  
}  
```  
  
```Output  
File size     : 732  
Drive         : C:  
Time modified : Thu Feb 07 14:39:36 2002  
```  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_access、_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)