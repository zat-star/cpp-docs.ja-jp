---
title: "_fullpath、_wfullpath | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fullpath
- _wfullpath
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
- wfullpath
- fullpath
- _wfullpath
- _fullpath
dev_langs: C++
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a1cc6a80609828d084b56ef4f981c9d03de8070
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fullpath-wfullpath"></a>_fullpath、_wfullpath
指定された相対パス名の絶対または完全パス名を作成します。  
  
## <a name="syntax"></a>構文  
  
```  
char *_fullpath(   
   char *absPath,  
   const char *relPath,  
   size_t maxLength   
);  
wchar_t *_wfullpath(   
   wchar_t *absPath,  
   const wchar_t *relPath,  
   size_t maxLength   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `absPath`  
 絶対または完全パス名を格納するバッファーへのポインター、または null。  
  
 `relPath`  
 相対パス名。  
  
 `maxLength`  
 絶対パス名のバッファー (`absPath`) の最大長。 この長さは、`_fullpath` の場合はバイト単位ですが、`wchar_t` の場合はワイド文字単位 (`_wfullpath`) です。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、絶対パス名 (`absPath`) を格納するバッファーへのポインターを返します。 エラーがある場合 (たとえば、`relPath` で渡される値に無効または見つからないドライブ文字が含まれている場合や、作成された絶対パス名 (`absPath`) の長さが `maxLength` よりも長い場合など)、この関数は `NULL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_fullpath`関数は、相対パス名で、展開`relPath`を完全修飾パスまたは絶対パスとストアの名前をこの`absPath`です。 `absPath` が null の場合、パス名を保持するための十分な長さのバッファーを割り当てるために `malloc` が使用されます。 このバッファーを解放するのは、呼び出し元の役目です。 相対パス名は、現在の場所から別の場所 (現在の作業ディレクトリ "." など) にパスを指定します。 絶対パス名は、ファイル システムのルートから目的の位置に到達するために必要なパス全体を示す相対パス名の拡張です。 `_makepath` とは異なり、`_fullpath` を使用して、名前に "./" または "../" が含まれる相対パス (`relPath`) の絶対パス名を取得できます。  
  
 たとえば、C ランタイム ルーチンを使用するには、アプリケーションに、ルーチンの宣言を含むヘッダー ファイルを含める必要があります。 各ヘッダー ファイルは、(アプリケーションの作業ディレクトリから) 相対的な方法でファイルの場所を参照するステートメントを含んでいます。  
  
```  
#include <stdlib.h>  
```  
  
 ファイルの絶対パス (実際のファイル システムの場所) は次のようになります。  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 `_fullpath` は、マルチバイト文字列引数を自動的に適切に処理し、現在使用しているマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識します。 `_wfullpath` は、`_fullpath` のワイド文字バージョンであり、`_wfullpath` の文字列引数はワイド文字列です。 `_wfullpath` がマルチバイト文字列を処理しない点を除き、`_wfullpath` と `_fullpath` の動作は同じです。  
  
 `_DEBUG` と `_CRTDBG_MAP_ALLOC` の両方が定義されている場合、`_fullpath` と `_wfullpath` への呼び出しは `_fullpath_dbg` と `_wfullpath_dbg` への呼び出しに置き換えられるので、メモリ割り当てをデバッグできます。 詳細については、「[_fullpath_dbg、_wfullpath_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)」を参照してください。  
  
 `maxlen` が 0 以下の場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`NULL` を返します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 `absPath` バッファーが `NULL` である場合、`_fullpath` は [malloc](../../c-runtime-library/reference/malloc.md) を呼び出してバッファーを割り当て、`maxLength` 引数を無視します。 このバッファーを ([free](../../c-runtime-library/reference/free.md) を使用して) 適切に解放するのは、呼び出し元の責任です。 `relPath` 引数がディスク ドライブを指定する場合、このドライブの現在のディレクトリがパスと結合されます。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_fullpath`|\<stdlib.h>|  
|`_wfullpath`|\<stdlib.h> または \<wchar.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_fullpath.c  
// This program demonstrates how _fullpath  
// creates a full path from a partial path.  
  
#include <stdio.h>  
#include <conio.h>  
#include <stdlib.h>  
#include <direct.h>  
  
void PrintFullPath( char * partialPath )  
{  
   char full[_MAX_PATH];  
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )  
      printf( "Full path is: %s\n", full );  
   else  
      printf( "Invalid path\n" );  
}  
  
int main( void )  
{  
   PrintFullPath( "test" );  
   PrintFullPath( "\\test" );  
   PrintFullPath( "..\\test" );  
}  
```  
  
```Output  
Full path is: C:\Documents and Settings\user\My Documents\test  
Full path is: C:\test  
Full path is: C:\Documents and Settings\user\test  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_getcwd、_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdcwd、_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [_makepath、_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_splitpath、_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)