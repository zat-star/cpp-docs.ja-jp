---
title: "_fullpath、_wfullpath | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fullpath"
  - "_wfullpath"
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
  - "wfullpath"
  - "fullpath"
  - "_wfullpath"
  - "_fullpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fullpath 関数"
  - "_wfullpath 関数"
  - "絶対パス"
  - "fullpath 関数"
  - "相対ファイル パス"
  - "wfullpath 関数"
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _fullpath、_wfullpath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定した相対パス名には、絶対パスでも完全パス名を作成します。  
  
## 構文  
  
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
  
#### パラメーター  
 `absPath`  
 格納するバッファーへのポインターは、絶対パスでも完全パス名、または NULL。  
  
 `relPath`  
 相対パス名。  
  
 `maxLength`  
 絶対パス名バッファー \(`absPath`\) の最大長。  この長さは `_fullpath` のバイトに、`_wfullpath`のワイド文字 \(`wchar_t`\) にあります。  
  
## 戻り値  
 これらの関数は、を格納しているバッファーへのポインターを絶対パス名 \(`absPath`\) を返します。  `relPath` で渡される値が無効または見つからないまたは作成された絶対パス名 \(`absPath`\) の長さが `maxLength`より大きい\) ドライブ文字が含まれている場合は、関数の戻り値 `NULL`エラーがある場合 \(たとえば。  
  
## 解説  
 `_fullpath` 関数は完全修飾パスまたは絶対パスに `relPath` の相対パス名を展開し、`absPath`でこの名前を格納します*。*`absPath` が NULL の場合はパス名を保持するのに十分な長さのバッファーを割り当てるには、`malloc` が使用されます。  これは、このバッファーの解放は、呼び出し元が保証します。  相対パス名を現在の場所から別の場所へのパスを指定します \(現在の作業ディレクトリなどの: 「。」\)。  絶対パス名には、ファイル システムのルートから目的の場所にアクセスするために必要なパス全体を参照する相対パス名の拡張です。  `_makepath`とは異なり「を含む相対パス \(`relPath`\) の絶対パス名を取得するために、`_fullpath` を使用できます。\/」または「。という名前です。  
  
 たとえば、C ランタイム ルーチンを使用する場合、アプリケーションはルーチンの宣言を含むヘッダー ファイルを含める必要があります。  各ヘッダー ファイルは相対的な方法でステートメントの参照をファイルの場所が含まれます \(アプリケーションの作業ディレクトリから\) :  
  
```  
#include <stdlib.h>  
```  
  
 ファイルの絶対パス \(実際のファイル システムの場所\) が次のようにしている場合:  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 `_fullpath` は現在使用中のマルチバイト コード ページに従ってマルチバイト文字列を認識し、必要に応じてマルチバイト文字列引数を自動的に処理します。  `_wfullpath`は `_fullpath`のワイド文字バージョンであり、; `_wfullpath`の文字列引数はワイド文字列です。  `_wfullpath`と `_fullpath`の動作は同じですが、`_wfullpath`はマルチバイト文字を処理しません。  
  
 `_DEBUG`と `_CRTDBG_MAP_ALLOC`の両方が定義されている場合、`_fullpath` の呼び出しと `_wfullpath` は `_fullpath_dbg` と `_wfullpath_dbg` の呼び出しとデバッグのメモリ割り当てを有効にするために置き換えられます。  詳細については、「[\_fullpath\_dbg、\_wfullpath\_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)」を参照してください。  
  
 この関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように `maxlen` が 0 以下の場合、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`NULL` を返します。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 `absPath` バッファーが `NULL`の場合、`_fullpath` はバッファーを割り当てるに [malloc](../../c-runtime-library/reference/malloc.md) を呼び出し、`maxLength` 引数を無視します。  必要に応じて、このバッファー \([フリー](../../c-runtime-library/reference/free.md)を使用して\) 解放する呼び出し元が保証します。  `relPath` の引数がディスク ドライブを指定すると、このドライブの現在のディレクトリがパスと結合されます。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_fullpath`|\<stdlib.h\>|  
|`_wfullpath`|\<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
  
  **完全パスは、次の操作: C:\\Documents と Settings\\user\\My Documents\\test**  
**完全パスは、次の操作: C:\\test**  
**完全パスは、次の操作: C:\\Documents と Settings\\user\\test**   
## 同等の .NET Framework 関数  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_getcwd、\_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdcwd、\_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [\_makepath、\_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_splitpath、\_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md)