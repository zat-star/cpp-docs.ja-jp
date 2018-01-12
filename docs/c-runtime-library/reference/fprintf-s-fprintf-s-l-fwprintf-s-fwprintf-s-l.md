---
title: "fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fprintf_s_l
- fwprintf_s
- fprintf_s
- _fwprintf_s_l
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
- _ftprintf_s
- fprintf_s
- fwprintf_s
dev_langs: C++
helpviewer_keywords:
- ftprintf_s_l function
- ftprintf_s function
- _fprintf_s_l function
- _ftprintf_s function
- _ftprintf_s_l function
- fwprintf_s_l function
- fwprintf_s function
- fprintf_s_l function
- fprintf_s function
- _fwprintf_s_l function
- print formatted data to streams
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9fc74164b44b44e9f2ed56066d91f68e232fceb7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fprintfs-fprintfsl-fwprintfs-fwprintfsl"></a>fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l
書式付きデータをストリームに出力します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [fprintf、_fprintf_l、fwprintf、_fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
int fprintf_s(   
   FILE *stream,  
   const char *format [,  
   argument_list ]  
);  
int _fprintf_s_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument_list ]  
);  
int fwprintf_s(   
   FILE *stream,  
   const wchar_t *format [,  
   argument_list ]  
);  
int _fwprintf_s_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument_list ]  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `format`  
 書式指定文字列。  
  
 `argument_list`  
 書式指定文字列に省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `fprintf_s` は、書き込まれたバイト数を返します。 `fwprintf_s` は、書き込まれたワイド文字数を返します。 これらの関数は、出力エラーが発生した場合、負の値を返します。  
  
## <a name="remarks"></a>コメント  
 `fprintf_s` は、一連の文字および値を書式設定し、出力 `stream` に出力します。 各引数は`argument_list`(存在する場合) は変換され、対応する書式指定に従って`format`です。 `format`引数は、 [printf 関数と wprintf 関数の指定の構文を書式設定](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)です。  
  
 `fwprintf_s` は `fprintf_s` のワイド文字バージョンで、`fwprintf_s` 内の `format` はワイド文字列です。 ストリームが ANSI モードで開かれている場合、これらの関数の動作は同じになります。 `fprintf_s` では、UNICODE ストリームへの出力はサポートされていません。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  
  
 セキュリティで保護されていないバージョン (「[fprintf、_fprintf_l、fwprintf、_fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)」を参照) と同様に、これらの関数も、`stream` または `format` パラメーターが null ポインターである場合には、パラメーターを検証して無効パラメーター ハンドラーを呼び出します (「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」を参照)。 書式指定文字列自体も検証されます。 未知の書式指定子や不適切な形式の書式指定子がある場合、これらの関数は無効なパラメーター例外を生成します。 すべての場合において、実行の継続が許可された場合、関数は -1 を返し、`errno` を `EINVAL` に設定します。 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ftprintf_s`|`fprintf_s`|`fprintf_s`|`fwprintf_s`|  
|`_ftprintf_s_l`|`_fprintf_s_l`|`_fprintf_s_l`|`_fwprintf_s_l`|  
  
 詳細については、[書式指定](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)に関するページを参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fprintf_s`, `_fprintf_s_l`|\<stdio.h>|  
|`fwprintf_s`, `_fwprintf_s_l`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```C  
// crt_fprintf_s.c  
// This program uses fprintf_s to format various  
// data and print it to the file named FPRINTF_S.OUT. It  
// then displays FPRINTF_S.OUT on the screen using the system  
// function to invoke the operating-system TYPE command.  
  
#include <stdio.h>  
#include <process.h>  
  
FILE *stream;  
  
int main( void )  
{  
   int    i = 10;  
   double fp = 1.5;  
   char   s[] = "this is a string";  
   char   c = '\n';  
  
   fopen_s( &stream, "fprintf_s.out", "w" );  
   fprintf_s( stream, "%s%c", s, c );  
   fprintf_s( stream, "%d\n", i );  
   fprintf_s( stream, "%f\n", fp );  
   fclose( stream );  
   system( "type fprintf_s.out" );  
}  
```  
  
```Output  
this is a string  
10  
1.500000  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_cprintf、_cprintf_l、_cwprintf、_cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf、_fscanf_l、fwscanf、_fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)