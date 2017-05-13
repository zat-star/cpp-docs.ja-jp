---
title: "_getcwd、_wgetcwd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
dev_langs:
- C++
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ad70ffac5cbe6cc7c56dbad0930bc87b969a1857
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="getcwd-wgetcwd"></a>_getcwd、_wgetcwd
現在の作業ディレクトリを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
char *_getcwd(   
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetcwd(   
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buffer`  
 パスの格納場所。  
  
 `maxlen`  
 文字数でのパスの最大長。 `char` の場合は `_getcwd` 、および `wchar_t` の場合は `_wgetcwd`。  
  
## <a name="return-value"></a>戻り値  
 `buffer`へのポインターを返します。 `NULL` 戻り値はエラーを示し、 `errno` は、 `ENOMEM`に設定され、 `maxlen` バイトを割り当てるのにメモリが不足している ( `NULL` の引数が `buffer`として指定されている場合) ことを示すか、または `ERANGE`に設定され、パスが `maxlen` 文字より長いことを示します。 `maxlen` が 0 以下の場合、この関数は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」(パラメーターの検証) で説明されているように無効なパラメーター ハンドラーを呼び出します。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_getcwd` 関数は、既定のドライブの現在の作業ディレクトリの完全なパスを取得し、それを `buffer`に格納します。 整数の引数 `maxlen` はパスの最大長を指定します。 パスの長さ (終端の null 文字を含む) が `maxlen`。 を超える場合、エラーが発生します。 `buffer` 引数は `NULL`になる可能性があります。パスを格納するため、 `maxlen` サイズ以上のバッファー (必要であればそれ以上) が `malloc`を使用して自動的に割り当てられます。 このバッファーは `free` を呼び出し、それに `_getcwd` の戻り値 (割り当てられるバッファーへのポインター) を渡すことにより、後で解放できます。  
  
 `_getcwd` は、現在の作業ディレクトリのパスを示す文字列を返します。 現在の作業ディレクトリがルートの場合、文字列は円記号 ( `\` ) で終わります。 現在の作業ディレクトリがルート以外のディレクトリの場合、文字列は、円記号ではなく、ディレクトリの名前で終わります。  
  
 ワイド文字を扱う場合は、`_wgetcwd` ではなく `_getcwd`を使用します。 `buffer` の場合、 `_wgetcwd` 引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 それ以外では、`_wgetcwd` と `_getcwd` の動作は同じです。  
  
 `_DEBUG` と `_CRTDBG_MAP_ALLOC` が定義されている場合、 `_getcwd` と `_wgetcwd` への呼び出しは `_getcwd_dbg` と `_wgetcwd_dbg` への呼び出しに置き換えられるので、メモリ割り当てをデバッグできます。 詳細については、「 [_getcwd_dbg, _wgetcwd_dbg](../../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd`|`_getcwd`|`_getcwd`|`_wgetcwd`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_getcwd`|\<direct.h>|  
|`_wgetcwd`|\<direct.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_getcwd.c  
// This program places the name of the current directory in the   
// buffer array, then displays the name of the current directory   
// on the screen. Passing NULL as the buffer forces getcwd to allocate  
// memory for the path, which allows the code to support file paths  
// longer than _MAX_PATH, which are supported by NTFS.  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* buffer;  
  
   // Get the current working directory:   
   if( (buffer = _getcwd( NULL, 0 )) == NULL )  
      perror( "_getcwd error" );  
   else  
   {  
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );  
      free(buffer);  
   }  
}  
```  
  
```Output  
C:\Code  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [_chdir、_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_mkdir、_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir、_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)
