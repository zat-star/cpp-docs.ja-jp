---
title: "_stat、_stat32、_stat64、_stati64、_stat32i64、_stat64i32、_wstat、_wstat32、_wstat64、_wstati64、_wstat32i64、_wstat64i32 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wstat64"
  - "_stati64"
  - "_stat32"
  - "_stat32i64"
  - "_stat"
  - "_wstati64"
  - "_wstat32"
  - "_wstat64i32"
  - "_wstat"
  - "_stat64"
  - "_stat64i32"
  - "_wstat32i64"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "tstat32"
  - "tstat"
  - "_tstat64i32"
  - "tstati64"
  - "_wstat64"
  - "_wstat32"
  - "wstati64"
  - "tstat64"
  - "_stati64"
  - "_wstat"
  - "wstat64i32"
  - "stat32i64"
  - "tstat32i64"
  - "_tstat"
  - "_wstati64"
  - "_tstati64"
  - "_wstat32i64"
  - "wstat32"
  - "_wstat64i32"
  - "_stat"
  - "_tstat32"
  - "stat64i32"
  - "wstat64"
  - "stat"
  - "_stat32i64"
  - "_stat32"
  - "stati64"
  - "wstat"
  - "_stat64i32"
  - "stat32"
  - "_tstat32i64"
  - "tstat64i32"
  - "_tstat64"
  - "_stat64"
  - "stat/_stat"
  - "stat/_stat32"
  - "stat/_stat64"
  - "stat/_stati64"
  - "stat/_stat32i64"
  - "stat/_stat64i32"
  - "stat/_wstat"
  - "stat/_wstat32"
  - "stat/_wstat64"
  - "stat/_wstati64"
  - "stat/_wstat32i64"
  - "stat/_wstat64i32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ファイル [C++]、ステータス情報"
  - "_stat 関数"
  - "_wstat 関数"
  - "_stat64i32 関数"
  - "tstat 関数"
  - "_tstat64i32 関数"
  - "_stati64 関数"
  - "_stat64 関数"
  - "tstati64 関数"
  - "wstati64 関数"
  - "wstat64 関数"
  - "_wstat64i32 関数"
  - "_tstat32i64 関数"
  - "_stat32i64 関数"
  - "stat 関数"
  - "ステータス (ファイルの)"
  - "_tstat32 関数"
  - "tstat64 関数"
  - "_wstat64 関数"
  - "_tstat 関数"
  - "_stat32 関数"
  - "wstat 関数"
  - "_wstat32i64 関数"
  - "_tstati64 関数"
  - "_wstat32 関数"
  - "stat64 関数"
  - "stati64 関数"
  - "_wstati64 関数"
  - "_tstat64 関数"
  - "ファイル [C++]、取得 (ステータス情報を)"
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
caps.latest.revision: 26
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _stat、_stat32、_stat64、_stati64、_stat32i64、_stat64i32、_wstat、_wstat32、_wstat64、_wstati64、_wstat32i64、_wstat64i32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルのステータス情報を取得します。  
  
## 構文  
  
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
  
#### パラメーター  
 `path`  
 既存のファイルやディレクトリのパスを含む文字列へのポインター。  
  
 `buffer`  
 結果を格納する構造体へのポインター。  
  
## 戻り値  
 これらの各関数は、ファイルのステータス情報が取得されると、0 を返します。 –1 という戻り値はエラーを示し、`errno` が `ENOENT` に設定されます \(ファイル名やパスが見つからなかったことを示します\)。`EINVAL` という戻り値は、無効なパラメーターを示します。この場合も `errno` は `EINVAL` に設定されます。  
  
 戻り値の詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 使用する場合は 1970 年 1 月 1 日午前 0 時から、UTC、3000 年 12 月 31 日 23時 59分: 59 秒前に、と後の場合、ファイルのタイムスタンプを表すことができます `_stat32` または `_wstat32`, を定義または `_USE_32BIT_TIME_T`, 、23時 59分: 59 2038 年 1 月 18 日 \(utc\) までの日付の表示にします。  
  
## 解説  
 `_stat` 関数は、`path` によって指定されるファイルやディレクトリに関する情報を取得し、`buffer` によって示される構造体にそれを格納します。`_stat` は、現在使用中のマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識し、マルチバイト文字列の引数を適切な方法で自動的に処理します。  
  
 `_wstat` 関数は、`_stat` 関数のワイド文字バージョンです。`path` 関数の引数 `_wstat` は、ワイド文字列です。`_wstat` がマルチバイト文字列を処理しない点を除き、`_wstat` と `_stat` の動作は同じです。  
  
 これらの関数のバリエーションは、32 ビットや 64 ビットの時刻型と、32 ビットや 64 ビットのファイル長をサポートします。 最初の数字のサフィックス \(`32` または `64`\) は、使用される時刻型のサイズを示します。2 番目のサフィックスは `i32` または `i64` で、ファイル サイズが 32 ビットの整数として表されるか、それとも 64 ビットの整数として表されるかを示します。  
  
 `_stat` 等価 `_stat64i32`, 、および `struct``_stat` 64 ビットの時刻が含まれています。 これは、該当しない限り、 `_USE_32BIT_TIME_T` が定義されている場合、以前の動作は有効です。 `_stat` 32 ビットの時刻を使用し、 `struct``_stat` 32 ビットの時刻が含まれています。 同じことが `_stati64` にも当てはまります。  
  
> [!NOTE]
>  `_wstat` は [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] シンボリック リンクでは機能しません。 この場合、`_wstat` は常に、ファイル サイズとして 0 を報告します。`_stat` は、シンボリック リンクで正しく機能します。  
  
 この関数は、パラメーターを検証します。`path` または `buffer` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、正しくないパラメーター ハンドラーが呼び出されます。  
  
### \_stat の時刻型とファイル長型のバリエーション  
  
|関数|\_USE\_32BIT\_TIME\_T が定義されているか|時刻型|ファイル長型|  
|--------|-------------------------------------|---------|------------|  
|`_stat`, `_wstat`|未定義|64 ビット|32 ビット|  
|`_stat`, `_wstat`|定義済み|32 ビット|32 ビット|  
|`_stat32`, `_wstat32`|マクロ定義の影響を受けない|32 ビット|32 ビット|  
|`_stat64`, `_wstat64`|マクロ定義の影響を受けない|64 ビット|64 ビット|  
|`_stati64`, `_wstati64`|未定義|64 ビット|64 ビット|  
|`_stati64`, `_wstati64`|定義済み|32 ビット|64 ビット|  
|`_stat32i64`, `_wstat32i64`|マクロ定義の影響を受けない|32 ビット|64 ビット|  
|`_stat64i32`, `_wstat64i32`|マクロ定義の影響を受けない|64 ビット|32 ビット|  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tstat`|`_stat`|`_stat`|`_wstat`|  
|`_tstat64`|`_stat64`|`_stat64`|`_wstat64`|  
|`_tstati64`|`_stati64`|`_stati64`|`_wstati64`|  
|`_tstat32i64`|`_stat32i64`|`_stat32i64`|`_wstat32i64`|  
|`_tstat64i32`|`_stat64i32`|`_stat64i32`|`_wstat64i32`|  
  
 `_stat` 構造体 \(SYS\\STAT.H で定義される\) には、次のフィールドが含まれています。  
  
 `st_gid`  
 ファイル \(UNIX 固有\) を所有するグループの数値 ID。Windows システムでは、このフィールドは常に 0 になります。 リダイレクトされたファイルは、Windows ファイルとして分類されます。  
  
 `st_atime`  
 ファイルに最後にアクセスした時刻。 NTFS では有効ですが、FAT 形式のディスク ドライブでは無効です。  
  
 `st_ctime`  
 ファイルの作成時刻。 NTFS では有効ですが、FAT 形式のディスク ドライブでは無効です。  
  
 `st_dev`  
 ファイルを含むディスクのドライブ番号 \(`st_rdev` と同じ\)。  
  
 `st_ino`  
 ファイル \(UNIX 固有\) の情報ノードの数 \(`inode`\)。 UNIX ファイル システムでは、`inode` は、ファイルの日時スタンプ、アクセス許可、コンテンツを記述します。 ファイルが互いにハードリンクされている場合、同じ `inode` を共有します。`inode`、そして必然的に `st_ino` は、FAT、HPFS、または NTFS ファイル システムでは意味がありません。  
  
 `st_mode`  
 ファイル モード情報のビット マスク。`path` がディレクトリを指定する場合、`_S_IFDIR` ビットが設定されます。`path` が通常のファイルまたはデバイスを指定する場合、`_S_IFREG` ビットが設定されます。 ユーザーの読み取り\/書き込みビットは、ファイルのアクセス許可モードに応じて設定されます。ユーザー実行ビットは、ファイル名の拡張子に応じて設定されます。  
  
 `st_mtime`  
 ファイルの最終変更時刻。  
  
 `st_nlink`  
 非 NTFS ファイル システムでは常に 1 です。  
  
 `st_rdev`  
 ファイルを含むディスクのドライブ番号 \(`st_dev` と同じ\)。  
  
 `st_size`  
 ファイルのサイズ \(バイト数\)。`i64` サフィックスを持つバリエーションの 64 ビットの整数**。**  
  
 `st_uid`  
 ファイルを所有するユーザーの数値識別子 \(UNIX 固有\)。 Windows システムでは、このフィールドは常に 0 です。 リダイレクトされたファイルは、Windows ファイルとして分類されます。  
  
 `path` がデバイスを参照する場合、`_stat` 構造体における `st_size`、各種時刻フィールド、`st_dev`、`st_rdev` フィールドには、意味がありません。 STAT.H はTYPES.Hで定義される [\_dev\_t](../../c-runtime-library/standard-types.md) 型を使用するため、コードで STAT.H の前に ES.H を組み込む必要があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|----------|------------|---------------|  
|`_stat`, `_stat32`, `_stat64`, `_stati64`, `_stat32i64`, `_stat64i32`|\<sys\/types.h\>、その後に \<sys\/stat.h\>|\<errno.h\>|  
|`_wstat`, `_wstat32`, `_wstat64`, `_wstati64`, `_wstat32i64`, `_wstat64i32`|\<sys\/types.h\>、その後に \<sys\/stat.h\> または \<wchar.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
ファイル サイズ     : 732 ドライブ         : C: 変更時刻: 2002 年 2 月 7 日 (木) 14:39:36  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::IO::File::GetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.getattributes.aspx)  
  
-   [System::IO::File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.getcreationtime.aspx)  
  
-   [System::IO::File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastaccesstime.aspx)  
  
-   [System::IO::File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastwritetime.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_access、\_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_fstat、\_fstat32、\_fstat64、\_fstati64、\_fstat32i64、\_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)