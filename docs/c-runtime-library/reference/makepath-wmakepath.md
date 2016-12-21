---
title: "_makepath、_wmakepath | Microsoft Docs"
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
  - "_makepath"
  - "_wmakepath"
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
  - "_wmakepath"
  - "_tmakepath"
  - "makepath"
  - "tmakepath"
  - "wmakepath"
  - "_makepath"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_makepath 関数"
  - "_tmakepath 関数"
  - "_wmakepath 関数"
  - "makepath 関数"
  - "パス"
  - "tmakepath 関数"
  - "wmakepath 関数"
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _makepath、_wmakepath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パス名の要素からパス名を作成します。  これらの関数のセキュリティを強化したバージョンについては、「[\_makepath\_s、\_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)」を参照してください。  
  
## 構文  
  
```  
void _makepath(  
   char *path,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
void _wmakepath(  
   wchar_t *path,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
```  
  
#### パラメーター  
 `path`  
 完全パス名のバッファー。  
  
 `drive`  
 目的のドライブに対応する文字 \(A、B など\) を指定します。後続のコロンは省略できます。  コロンを省略した場合、`_makepath` によって、コロンが自動的にパス名に挿入されます。  `drive` が `NULL` の場合、または空の文字列を指す場合、作成される `path` 文字列にドライブ文字は含まれません。  
  
 `dir`  
 ドライブ指定子と実際のファイル名を除いて、ディレクトリのパスを指定します。  後続のスラッシュまたは円記号は省略できます。1 つの `dir` 引数には、スラッシュ \(\/\) か円記号 \(\\\)、またはその両方を使用することもできます。  後続のスラッシュ \(\/\) または円記号 \(\\\) は、指定しなくても自動的に挿入されます。  `dir` が `NULL` の場合、または空の文字列を指す場合、作成される `path` 文字列にディレクトリのパスは挿入されません。  
  
 `fname`  
 拡張子の付いていない基本ファイル名を指定します。  `fname` が `NULL` の場合、または空の文字列を指す場合、作成される `path` 文字列にファイル名は挿入されません。  
  
 `ext`  
 実際のファイル名の拡張子を指定します。先頭のピリオド \(.\) は省略できます。  `ext` にピリオドがない場合、`_makepath` によって自動的にピリオドが挿入されます。  `ext` が `NULL` の場合、または空の文字列を指す場合、作成される `path` 文字列に拡張子は挿入されません。  
  
## 解説  
 `_makepath` 関数は、各構成要素からパスの文字列を作成し、結果を `path` に格納します。  `path` には、ドライブ文字、ディレクトリのパス、ファイル名、およびファイル名の拡張子が含まれます。  `_wmakepath` は `_makepath` のワイド文字バージョンであり、`_wmakepath` の引数はワイド文字列です。  それ以外では、`_wmakepath` と `_makepath` の動作は同じです。  
  
 **セキュリティに関するメモ** null で終わる文字列を使用してください。  バッファー オーバーランを避けるために、null で終わる文字列は `path` バッファーのサイズを超えないようにしてください。  `_makepath` では、作成されるパス文字列の長さが `_MAX_PATH` を超えないことは保証されません。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 `path` 引数は、絶対パスを保持するのに十分な大きさの空きバッファーを指す必要があります。  作成される `path` の長さは、Stdlib.h に定義されている定数 `_MAX_PATH` を超えることはできません。  
  
 パスが `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  さらに、`errno` が `EINVAL` に設定されます。  他のすべてのパラメーターでは、`NULL` 値が許容されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_makepath`|\<stdlib.h\>|  
|`_wmakepath`|\<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_makepath.c  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
  
   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996  
   // Note: _makepath is deprecated; consider using _makepath_s instead  
   printf( "Path created with _makepath: %s\n\n", path_buffer );  
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996  
   // Note: _splitpath is deprecated; consider using _splitpath_s instead  
   printf( "Path extracted with _splitpath:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
  **\_makepath で作成されたパス: c:\\sample\\crt\\makepath.c**  
**\_splitpath で取得したパス:**  
 **ドライブ: c:**  
 **ディレクトリ: \\sample\\crt\\**  
 **ファイル名: makepath**  
 **Ext: .c**   
## 同等の .NET Framework 関数  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_fullpath、\_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath、\_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md)   
 [\_makepath\_s、\_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)