---
title: "_vsprintf_p、_vsprintf_p_l、_vswprintf_p、_vswprintf_p_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _vsprintf_p
- _vswprintf_p
- _vsprintf_p_l
- _vswprintf_p_l
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
apitype: DLLExport
f1_keywords:
- vsprintf_p
- _vswprintf_p
- _vstprintf_p
- vswprintf_p
- _vsprintf_p
- vstprintf_p
dev_langs: C++
helpviewer_keywords:
- vstprintf_p_l function
- _vsprintf_p_l function
- _vstprintf_p function
- vsprintf_p_l function
- _vswprintf_p function
- vswprintf_p function
- vsprintf_p function
- vswprintf_p_l function
- _vswprintf_p_l function
- vstprintf_p function
- formatted text [C++]
- _vsprintf_p function
- _vstprintf_p_l function
ms.assetid: 00821c0d-9fee-4d8a-836c-0669cfb11317
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d64200b38fb206426b037c0c12d008739e0509b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="vsprintfp-vsprintfpl-vswprintfp-vswprintfpl"></a>_vsprintf_p、_vsprintf_p_l、_vswprintf_p、_vswprintf_p_l
引数リストへのポインターを使用して、書式付き出力を書き込みます。その際、引数を使用する順序を指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
int _vsprintf_p(  
   char *buffer,  
   size_t sizeInBytes,  
   const char *format,  
   va_list argptr   
);   
int _vsprintf_p_l(  
   char *buffer,  
   size_t sizeInBytes,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);   
int _vswprintf_p(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vswprintf_p_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buffer`  
 出力の格納位置。  
  
 `sizeInBytes`  
 文字内の `buffer` のサイズ。  
  
 `count`  
 この関数の Unicode バージョンで格納する最大文字数。  
  
 `format`  
 書式の指定。  
  
 `argptr`  
 引数リストへのポインター。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `_vsprintf_p` 関数と `_vswprintf_p` 関数は、書き込まれた文字数を返します。終端の null 文字は含まれません。出力エラーが発生した場合は、負の値を返します。  
  
## <a name="remarks"></a>コメント  
 これらの関数は、引数リストへのポインターを使用し、指定されたデータを書式指定して `buffer` が指すメモリに書き込みます。  
  
 これらの関数は、位置指定パラメーターをサポートする点を除いて `vsprintf_s` および `vswprintf_s` と同じです。 詳細については、「[printf_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)」をご覧ください。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 `buffer` または `format` パラメーターが Null ポインターの場合、カウントがゼロの場合、または書式指定文字列に無効な書式指定文字が含まれている場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は -1 を返し、`errno` を `EINVAL` に設定します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vstprintf_p`|`_vsprintf_p`|`_vsprintf_p`|`_vswprintf_p`|  
|`_vstprintf_p_l`|`_vsprintf_p_l`|`_vsprintf_p_l`|`_vswprintf_p_l`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|  
|-------------|---------------------|----------------------|  
|`_vsprintf_p`, `_vsprintf_p_l`|\<stdio.h> および \<stdarg.h>|\<varargs.h>*|  
|`_vswprintf_p`, `_vswprintf_p_l`|\<stdio.h> または \<wchar.h>、および \<stdarg.h>|\<varargs.h>*|  
  
 \* UNIX V との互換性用。  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt__vsprintf_p.c  
// This program uses vsprintf_p to write to a buffer.  
// The size of the buffer is determined by _vscprintf_p.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <stdarg.h>  
  
void example( char * format, ... )  
{  
    va_list  args;  
    int      len;  
    char     *buffer = NULL;  
  
    va_start( args, format );  
  
    // _vscprintf doesn't count the   
    // null terminating string so we add 1.  
    len = _vscprintf_p( format, args ) + 1;  
  
    // Allocate memory for our buffer  
    buffer = (char*)malloc( len * sizeof(char) );  
    if (buffer)  
    {  
        _vsprintf_p( buffer, len, format, args );  
        puts( buffer );  
        free( buffer );  
    }  
    va_end( args );
}  
  
int main( void )  
{  
    // First example  
    example( "%2$d %1$c %3$d", '<', 123, 456 );  
  
    // Second example  
    example( "%s", "This is a string" );  
}  
```  
  
```Output  
123 < 456  
This is a string  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf、_fprintf_l、fwprintf、_fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg、va_copy、va_end、va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)