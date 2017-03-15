---
title: "_futime、_futime32、_futime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_futime64"
  - "_futime32"
  - "_futime"
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
  - "futime"
  - "_futime"
  - "futime64"
  - "_futime64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_futime 関数"
  - "futime32 関数"
  - "futime64 関数"
  - "ファイルの変更時刻 [C++]"
  - "_futime64 関数"
  - "futime 関数"
  - "_futime32 関数"
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _futime、_futime32、_futime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

開いているファイルの変更時刻を設定します。  
  
## 構文  
  
```  
int _futime(   
   int fd,  
   struct _utimbuf *filetime   
);  
int _futime32(   
   int fd,  
   struct __utimbuf32 *filetime   
);  
int _futime64(   
   int fd,  
   struct __utimbuf64 *filetime   
);  
```  
  
#### パラメーター  
 `fd`  
 開いているファイルへのファイル記述子を返します。  
  
 `filetime`  
 含む構造体へのポインター変更日新しい。  
  
## 戻り値  
 正常終了した場合は 0 を返します。  エラーが発生した場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、無効なパラメーターを示す `EBADF`設定され、無効なファイル記述子を `EINVAL`への関数の戻り値–1 と `errno` を示します。  
  
## 解説  
 `_futime` ルーチンは `fd`に関連付けられているファイルの変更日とアクセス時刻を設定します*。* `_futime` は [\_utime](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)と同じですが、引数にファイルまたはファイル パス名ではなく、開いているファイルへのファイル記述子です。  `_utimbuf` 構造体は新しい変更日とアクセス時刻のフィールドが含まれています。  フィールドは、有効な値を含める必要があります。  `_utimbuf32` と `_utimbuf64` は、32 ビットと 64 ビットの時刻型の使用を除き、それぞれ `_utimbuf` と同じです。  `_futime` と `_utimbuf` は 64 ビットの時刻型を使用し、`_futime` は `_futime64`と動作は同じです。  古い動作を強制的に実行する必要がある場合 `_USE_32BIT_TIME_T`を定義します。  これを行うには `_futime32` に `_futime` を動作が同一にし、`_utimbuf` 構造体に `__utimbuf32`と同じにする 32 ビットの時刻型を使用します。  
  
 `_futime64`は 23:59 で `__utimbuf64` 構造体を使用するファイルの日付を読み取って変更する: 59、3000 12 年 10 月 31 日は、UTC; ファイルの日付が 19:14 よりも後の場合は `_futime32` への呼び出しが失敗する場合: 1 年 1 月 07 日 18 時 2038、UTC。  午前 1970 は 1 年 2 月 1 日に、これらの関数の日付範囲の下限です。  
  
## 必要条件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------|------------|----------------|  
|`_futime`|\<sys\/utime.h\>|\<errno.h\>|  
|`_futime32`|\<sys\/utime.h\>|\<errno.h\>|  
|`_futime64`|\<sys\/utime.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_futime.c  
// This program uses _futime to set the  
// file-modification time to the current time.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <io.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/utime.h>  
#include <share.h>  
  
int main( void )  
{  
   int hFile;  
  
   // Show file time before and after.   
   system( "dir crt_futime.c_input" );  
  
   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );  
  
   if( _futime( hFile, NULL ) == -1 )  
      perror( "_futime failed\n" );  
   else  
      printf( "File time modified\n" );  
  
   _close (hFile);  
  
   system( "dir crt_futime.c_input" );  
}  
```  
  
## 入力: crt\_futime.c\_input  
  
```  
Arbitrary file contents.  
```  
  
### 出力例  
  
```  
Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:40 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
 Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:41 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
File time modified  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::IO::File::SetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastaccesstime.aspx)  
  
-   [System::IO::File::SetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastwritetime.aspx)  
  
-   [System::IO::File::SetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.setcreationtime.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)