---
title: "_makepath_s、_wmakepath_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmakepath_s"
  - "_makepath_s"
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
  - "_wmakepath_s"
  - "makepath_s"
  - "_makepath_s"
  - "wmakepath_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_makepath_s 関数"
  - "wmakepath_s 関数"
  - "パス"
  - "_wmakepath_s 関数"
  - "makepath_s 関数"
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _makepath_s、_wmakepath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パス名の要素からパス名を作成します。  これらの関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_makepath、\_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t _makepath_s(  
   char *path,  
   size_t sizeInBytes,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
errno_t _wmakepath_s(  
   wchar_t *path,  
   size_t sizeInWords,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
template <size_t size>  
errno_t _makepath_s(  
   char (&path)[size],  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
); // C++ only  
template <size_t size>  
errno_t _wmakepath_s(  
   wchar_t (&path)[size],  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
); // C++ only  
```  
  
#### パラメーター  
 \[出力\] `path`  
 完全パス名のバッファー。  
  
 \[入力\] `sizeInWords`  
 バッファーのサイズ \(ワード数\)。  
  
 \[入力\] `sizeInBytes`  
 バッファーのサイズ \(バイト数\)。  
  
 \[入力\] `drive`  
 目的のドライブに対応する文字 \(A、B など\) を指定します。後続のコロンは省略できます。  コロンを省略した場合、`_makepath_s` によって、コロンが自動的にパス名に挿入されます。  `drive` が `NULL` の場合、または空の文字列を指す場合、作成される `path` 文字列にドライブ文字は含まれません。  
  
 \[入力\] `dir`  
 ドライブ指定子と実際のファイル名を除いて、ディレクトリのパスを指定します。  後続のスラッシュまたは円記号は省略できます。1 つの `dir` 引数には、スラッシュ \(\/\) か円記号 \(\\\)、またはその両方を使用することもできます。  後続のスラッシュ \(\/\) または円記号 \(\\\) は、指定しなくても自動的に挿入されます。  `dir` が `NULL` の場合、または空の文字列を指す場合、作成される `path` 文字列にディレクトリのパスは挿入されません。  
  
 \[入力\] `fname`  
 拡張子の付いていない基本ファイル名を指定します。  `fname` が `NULL` の場合、または空の文字列を指す場合、作成される `path` 文字列にファイル名は挿入されません。  
  
 \[入力\] `ext`  
 実際のファイル名の拡張子を指定します。先頭のピリオド \(.\) は省略できます。  `ext` にピリオドがない場合、`_makepath_s` によって自動的にピリオドが挿入されます。  `ext` が `NULL` の場合、または空の文字列を指す場合、作成される `path` 文字列に拡張子は挿入されません。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
### エラー条件  
  
|`path`|`sizeInWords` \/ `sizeInBytes`|戻り値|`path` の内容|  
|------------|------------------------------------|---------|----------------|  
|`NULL`|任意|`EINVAL`|変更されない|  
|任意|\<\= 0|`EINVAL`|変更されない|  
  
 上のいずれかのエラー条件が発生すると、これらの関数は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続 `errno` は`EINVAL` に設定され、関数から`EINVAL`\#\#\#.`NULL` はパラメーター `drive`、`fname`と `ext`で使用されます。  これらのパラメーターが null ポインターまたは空の文字列である場合の動作については、「解説」を参照してください。  
  
## 解説  
 `_makepath_s` 関数は、各構成要素からパスの文字列を作成し、結果を `path` に格納します。  `path` には、ドライブ文字、ディレクトリのパス、ファイル名、およびファイル名の拡張子が含まれます。  `_wmakepath_s` は `_makepath_s` のワイド文字バージョンであり、`_wmakepath_s` の引数はワイド文字列です。  それ以外では、`_wmakepath_s` と `_makepath_s` の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tmakepath_s`|`_makepath_s`|`_makepath_s`|`_wmakepath_s`|  
  
 `path` 引数は、絶対パスを保持するのに十分な大きさの空きバッファーを指す必要があります。  作成される `path` の長さは、Stdlib.h に定義されている定数 `_MAX_PATH` を超えることはできません。  
  
 パスが `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  さらに、`errno` が `EINVAL` に設定されます。  他のすべてのパラメーターでは、`NULL` 値が許容されます。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
 これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。  この動作を無効にするには、[\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) を使用します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_makepath_s`|\<stdlib.h\>|  
|`_wmakepath_s`|\<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_makepath_s.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
   errno_t err;  
  
   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",  
                      "crt_makepath_s", "c" );  
   if (err != 0)  
   {  
      printf("Error creating path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );  
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,  
                       _MAX_FNAME, ext, _MAX_EXT );  
   if (err != 0)  
   {  
      printf("Error splitting the path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path extracted with _splitpath_s:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
## 出力  
  
```  
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c  
  
Path extracted with _splitpath_s:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: crt_makepath_s  
  Ext: .c  
```  
  
## 同等の .NET Framework 関数  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_fullpath、\_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath\_s、\_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)   
 [\_makepath、\_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)