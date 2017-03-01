---
title: "_searchenv_s、_wsearchenv_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsearchenv_s
- _searchenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
dev_langs:
- C++
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
caps.latest.revision: 32
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: c70908d3c884eed962560e0a5284c66c3c234a7e
ms.lasthandoff: 02/24/2017

---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s、_wsearchenv_s
環境のパスを使用してファイルを検索します。 これらの [_searchenv および _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md) のバージョンは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」(CRT のセキュリティ機能) で説明されているように、セキュリティが強化されています。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char *pathname,  
   size_t numberOfElements  
);  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `filename`  
 検索するファイルの名前。  
  
 [入力] `varname`  
 検索する環境。  
  
 [出力] `pathname`  
 完全パスを格納するバッファー。  
  
 [入力] `numberOfElements`  
 `pathname` バッファーのサイズ。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は&0; を返します。失敗した場合はエラー コードを返します。  
  
 `filename` に空の文字列が指定された場合は、返値は `ENOENT` になります。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`filename`|`varname`|`pathname`|`numberOfElements`|戻り値|`pathname` の内容|  
|----------------|---------------|----------------|------------------------|------------------|----------------------------|  
|任意|任意|`NULL`|任意|`EINVAL`|適用なし|  
|`NULL`|任意|任意|任意|`EINVAL`|変更されない|  
|任意|任意|任意|<= 0|`EINVAL`|変更されない|  
  
 上記のいずれかのエラー条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラ―が呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_searchenv_s` ルーチンは、指定したドメインでターゲット ファイルを検索します。 `varname` 変数は、`PATH`、`LIB`、および `INCLUDE` などのディレクトリ パスのリストを指定する環境変数またはユーザー定義変数です。 `_searchenv_s` では大文字と小文字が区別されるため、`varname` は環境変数と大文字小文字が一致する必要があります。 `varname` がプロセスの環境で定義されている環境変数の名前と一致しない場合、関数は&0; を返し、`pathname` 変数は変更されません。  
  
 このルーチンは最初に現在の作業ディレクトリでファイルを検索します。 ファイルが見つからなかった場合、環境変数で指定されている次のディレクトリを検索します。 ターゲット ファイルがこれらのディレクトリのいずれかで見つかった場合は、新しく作成されたパスを `pathname` にコピーします。 `filename` ファイルが見つからない場合、`pathname` には null で終わる空の文字列が挿入されます。  
  
 `pathname` バッファーは、`_MAX_PATH` 以上の文字数にして、作成されるパス名の最大の長さに対応できるようにする必要があります。 長さが足りないと、`_searchenv_s` で `pathname` バッファーのオーバーランが発生し、予期しない動作が生じる場合があります。  
  
 `_wsearchenv_s` は `_searchenv_s` のワイド文字バージョンであり、`_wsearchenv_s` の引数はワイド文字列です。 それ以外では、`_wsearchenv_s` と `_searchenv_s` の動作は同じです。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsearchenv_s`|`_searchenv_s`|`_searchenv_s`|`_wsearchenv_s`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_searchenv_s`|\<stdlib.h>|  
|`_wsearchenv_s`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_searchenv_s.c  
/* This program searches for a file in  
 * a directory specified by an environment variable.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
   errno_t err;  
  
   /* Search for file in PATH environment variable: */  
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );  
   if (err != 0)  
   {  
      printf("Error searching the path. Error code: %d\n", err);  
   }  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
```Output  
Path for CL.EXE:  
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [_searchenv、_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)   
 [getenv、_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_putenv、_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)
