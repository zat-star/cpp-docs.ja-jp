---
title: "_chsize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chsize"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_chsize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chsize 関数"
  - "chsize 関数"
  - "ファイル [C++], 変更 (サイズを)"
  - "サイズ"
  - "サイズ, 変更 (ファイルを)"
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _chsize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルのサイズを変更します。  セキュリティが強化されたバージョンを使用して; [\_chsize\_s](../../c-runtime-library/reference/chsize-s.md)を参照してください。  
  
## 構文  
  
```  
int _chsize(   
   int fd,  
   long size   
);  
```  
  
#### パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
 `size`  
 バイトのファイルの新しい長さ。  
  
## 戻り値  
 `_chsize` は ファイル サイズが正常に変更された場合は値 0 を返します。  –1 の戻り値はエラーを示します: `errno` は `EBADF`、`ENOSPC` への `EACCES` に `size` が小さい場合領域がデバイスに残っている場合、または `EINVAL` 設定され、指定したファイルが読み取り専用であるか、記述子が無効な場合、指定したファイルがアクセスに対してロックされる場合。  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_chsize` 関数は `size`で指定された長さに `fd` に関連付けられたファイルを拡張するか、切り捨てられます。  ファイルはモードで開く必要ための書き込み。  ファイルがまで null 文字 \(「\\0」\) が付けられます。  ファイルが切り詰められている場合、簡略化されたファイルの末尾からファイルの元の長さへのすべてのデータは失われます。  
  
 この関数は、パラメーターを検証します。  ゼロまたは `fd` 不正なファイル記述子が `size` 未満である場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_chsize`|\<io.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_chsize.c  
// This program uses _filelength to report the size  
// of a file before and after modifying it with _chsize.  
  
#include <io.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh, result;  
   unsigned int nbytes = BUFSIZ;  
  
   // Open a file   
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,  
                 _S_IREAD | _S_IWRITE ) == 0 )  
   {  
      printf( "File length before: %ld\n", _filelength( fh ) );  
      if( ( result = _chsize( fh, 329678 ) ) == 0 )  
         printf( "Size successfully changed\n" );  
      else  
         printf( "Problem in changing the size\n" );  
      printf( "File length after:  %ld\n", _filelength( fh ) );  
      _close( fh );  
   }  
}  
```  
  
  **前にファイル長: 0**  
**正常に変更できるサイズ**  
**後でファイル長:  329678**   
## 同等の .NET Framework 関数  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_close](../Topic/_close.md)   
 [\_sopen、\_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)