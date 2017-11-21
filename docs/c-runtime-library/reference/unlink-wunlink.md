---
title: "_unlink、_wunlink | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _unlink
- _wunlink
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
- _tunlink
- _unlink
- wunlink
- _wunlink
dev_langs: C++
helpviewer_keywords:
- files [C++], deleting
- _wunlink function
- wunlink function
- unlink function
- _unlink function
- tunlink function
- files [C++], removing
- _tunlink function
ms.assetid: 5e4f5f1b-1e99-4391-9b18-9ac63c32fae8
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e98fb76faad72cedf48d8cc6baa7113870273d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="unlink-wunlink"></a>_unlink、_wunlink
ファイルを削除します。  
  
## <a name="syntax"></a>構文  
  
```  
int _unlink(  
   const char *filename   
);  
int _wunlink(  
   const wchar_t *filename   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `filename`  
 削除するファイルの名前。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、これらの各関数は 0 を返します。 関数は-1 を返しますそれ以外の場合、およびセット`errno`に`EACCES`、読み取り専用ファイル、つまり、パスを指定しますまたは`ENOENT`ファイルまたはパスが見つからない、またはパスがディレクトリを指定します。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_unlink` 関数は、`filename` によって指定されたファイルを削除します。 `_wunlink` 関数は、`_unlink` 関数のワイド文字バージョンです。`filename` 関数の引数 `_wunlink` は、ワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tunlink`|`_unlink`|`_unlink`|`_wunlink`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_unlink`|\<io.h> および \<stdio.h>|  
|`_wunlink`|\<io.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="code-example"></a>コード例  
 このプログラムは、_unlink を使用して CRT_UNLINK.TXT を削除します。  
  
```  
// crt_unlink.c  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( _unlink( "crt_unlink.txt" ) == -1 )  
      perror( "Could not delete 'CRT_UNLINK.TXT'" );  
   else  
      printf( "Deleted 'CRT_UNLINK.TXT'\n" );  
}  
```  
  
### <a name="input-crtunlinktxt"></a>入力: crt_unlink.txt  
  
```  
This file will be deleted.  
```  
  
### <a name="sample-output"></a>出力例  
  
```  
Deleted 'CRT_UNLINK.TXT'  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [remove、_wremove](../../c-runtime-library/reference/remove-wremove.md)