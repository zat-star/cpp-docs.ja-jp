---
title: "_searchenv、_wsearchenv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_searchenv"
  - "_wsearchenv"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wsearchenv"
  - "_tsearchenv"
  - "wsearchenv"
  - "_searchenv"
  - "searchenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_searchenv 関数"
  - "_tsearchenv 関数"
  - "_wsearchenv 関数"
  - "環境パス"
  - "環境パス, 検索 (ファイルを)"
  - "ファイル [C++], 検索"
  - "searchenv 関数"
  - "tsearchenv 関数"
  - "wsearchenv 関数"
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# _searchenv、_wsearchenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルを検索するために環境パスを使用します。  これらの関数のセキュリティを強化したバージョンについては、「[\_searchenv\_s、\_wsearchenv\_s](../Topic/_searchenv_s,%20_wsearchenv_s.md)」を参照してください。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char *pathname   
);  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname   
);  
template <size_t size>  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### パラメーター  
 `filename`  
 検索するファイルの名前。  
  
 `varname`  
 検索する環境。  
  
 `pathname`  
 完全パスを格納するバッファー。  
  
## 解説  
 `_searchenv` ルーチンは、指定したドメインでターゲット ファイルを検索します。  `varname` 変数は、`PATH`、`LIB`、または `INCLUDE` などのディレクトリ パスのリストを指定する任意の環境変数またはユーザー定義変数です。  `_searchenv` では大文字と小文字が区別されるため、`varname` は環境変数と大文字小文字が一致する必要があります。  
  
 このルーチンは最初に現在の作業ディレクトリでファイルを検索します。  ファイルが見つからなかった場合、環境変数で指定されているディレクトリを検索します。  ターゲット ファイルがこれらのディレクトリのいずれかで見つかった場合は、新しく作成されたパスを `pathname` にコピーします。  `filename` ファイルが見つからない場合、`pathname` には null で終わる空の文字列が挿入されます。  
  
 `pathname` バッファーは、`_MAX_PATH` 以上の文字数にして、作成されるパス名の最大の長さに対応できるようにする必要があります。  長さが足りないと、`_searchenv` で `pathname` バッファーのオーバーランが発生し、予期しない動作が発生することがあります。  
  
 `_wsearchenv` は `_searchenv` のワイド文字バージョンであり、`_wsearchenv` の引数はワイド文字列です。  それ以外では、`_wsearchenv` と `_searchenv` の動作は同じです。  
  
 `filename` が空の文字列の場合は、これらの関数は `ENOENT` を返します。  
  
 `filename` または `pathname` が `NULL` ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
 `errno` とエラー コードの詳細については、「[errno 定数](../../c-runtime-library/errno-constants.md)」を参照してください。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティを強化された新しい関数を呼び出します。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tsearchenv`|`_searchenv`|`_searchenv`|`_wsearchenv`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_searchenv`|\<stdlib.h\>|  
|`_wsearchenv`|\<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_searchenv.c  
// compile with: /W3  
// This program searches for a file in  
// a directory that's specified by an environment variable.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
  
   // Search for file in PATH environment variable:  
   _searchenv( searchfile, envvar, pathbuffer ); // C4996  
   // Note: _searchenv is deprecated; consider using _searchenv_s  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
  **CL.EXE のパス:**  
**C:\\Program Files\\Microsoft Visual Studio 8\\VC\\BIN\\CL.EXE**   
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [getenv、\_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_putenv、\_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [\_searchenv\_s、\_wsearchenv\_s](../Topic/_searchenv_s,%20_wsearchenv_s.md)