---
title: "sprintf_s、_sprintf_s_l、swprintf_s、_swprintf_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _swprintf_s_l
- _sprintf_s_l
- swprintf_s
- sprintf_s
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
- swprintf_s
- sprintf_s
- stdio/sprintf_s
- stdio/swprintf_s
- stdio/_sprintf_s_l
- stdio/_swprintf_s_l
- _sprintf_s_l
- _swprintf_s_l
dev_langs: C++
helpviewer_keywords:
- stprintf_s function
- stprintf_s_l function
- swprintf_s_l function
- sprintf_s function
- swprintf_s function
- _swprintf_s_l function
- sprintf_s_l function
- _stprintf_s_l function
- _stprintf_s function
- _sprintf_s_l function
- formatted text [C++]
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e1dda25ab045262dffb34085519f4cf8b8bf226c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="sprintfs-sprintfsl-swprintfs-swprintfsl"></a>sprintf_s、_sprintf_s_l、swprintf_s、_swprintf_s_l
文字列に書式付きデータを書き込みます。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
int sprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   ...   
);  
int _sprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale,  
   ...   
);  
int swprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   ...  
);  
int _swprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale,  
   ...  
);  
template <size_t size>  
int sprintf_s(  
   char (&buffer)[size],  
   const char *format,  
   ...   
); // C++ only  
template <size_t size>  
int swprintf_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   ...  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buffer`  
 出力の格納場所。  
  
 `sizeOfBuffer`  
 格納する最大文字数。  
  
 `format`  
 書式指定文字列。  
  
 `...`  
 書式設定する省略可能な引数  
  
 `locale`  
 使用するロケール。  
  
 詳細については、「 [printf 関数と wprintf 関数の書式指定フィールド](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」を参照してください。  
  
## <a name="return-value"></a>戻り値  
 書き込まれた文字数またはエラーが発生した場合は-1。 `buffer` または `format` が null ポインターである場合、 `sprintf_s` および `swprintf_s` は -1 を返し、 `errno` を `EINVAL`に設定します。  
  
 `sprintf_s` 関数は、 `buffer`に格納されているバイト数を返します。終端の null 文字は含まれません。 `swprintf_s` は、`buffer` に格納されているワイド文字数を返します。終端の null ワイド文字は含まれません。  
  
## <a name="remarks"></a>コメント  
 `sprintf_s` 関数は、一連の文字と値の書式を指定して、 `buffer`に格納します。 各 `argument` (指定されている場合) は、 `format`中の対応する書式指定に応じて変換され、格納されます。 format は通常の文字で構成し、その形式と機能は `format` printf [関数の](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)と同じです。 最後に書き込まれる文字の後に NULL 文字が追加されます。 重なり合う文字列間でコピーした場合の動作は未定義です。  
  
 `sprintf_s` と `sprintf` 間の主な違いとしては、 `sprintf_s` は書式指定文字列の有効な書式指定文字をチェックしますが、 `sprintf` は書式指定文字列またはバッファーが `NULL` ポインターかどうかのみをチェックします。 いずれかのチェックが失敗した場合、「 [Parameter Validation](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は -1 を返し、 `errno` を `EINVAL`に設定します。  
  
 `sprintf_s` と `sprintf` 間のもう 1 つの違いとして、 `sprintf_s` は、出力バッファーのサイズを文字数で指定する長さパラメーターを受け取ります。 バッファーが、終端の null を含めた書式付きテキストに対して小さすぎる場合は、バッファーは `buffer[0]`で null 文字を配置することで空の文字列に設定され、無効なパラメーター ハンドラーが呼び出されます。 `_snprintf`とは異なり、 `sprintf_s` では、バッファー サイズがゼロでない限り、必ずバッファーは null で終わります。  
  
 `swprintf_s` は `sprintf_s`のワイド文字バージョンであり、 `swprintf_s` のポインター引数はワイド文字列です。 `swprintf_s` と `sprintf_s` では、エンコーディング エラーの検出動作が異なる場合があります。 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
 `sprintf_s` には、バッファーが小さすぎる場合に発生する状況を制御できるバージョンもあります。 詳細については、「 [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stprintf_s`|`sprintf_s`|`sprintf_s`|`swprintf_s`|  
|`_stprintf_s_l`|`_sprintf_s_l`|`_sprintf_s_l`|`_swprintf_s_l`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`sprintf_s`、 `_sprintf_s_l`|C: \<stdio.h><br /><br /> C++: \<cstdio> または \<stdio.h>|  
|`swprintf_s`、 `_swprintf_s_l`|C: \<stdio.h> または \<wchar.h><br /><br /> C++: \<cstdio>、\<cwchar>、\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_sprintf_s.c  
// This program uses sprintf_s to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf_s( buffer, 200,     "   String:    %s\n", s );  
   j += sprintf_s( buffer + j, 200 - j, "   Character: %c\n", c );  
   j += sprintf_s( buffer + j, 200 - j, "   Integer:   %d\n", i );  
   j += sprintf_s( buffer + j, 200 - j, "   Real:      %f\n", fp );  
  
   printf_s( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
}  
```  
  
```Output  
Output:  
   String:    computer  
   Character: l  
   Integer:   35  
   Real:      1.732053  
  
character count = 79  
```  
  
## <a name="example"></a>例  
  
```  
// crt_swprintf_s.c  
// wide character example  
// also demonstrates swprintf_s returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf_s( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf_s( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf_s fails because string contains WEOF (\xffff)  
   printf( "wrote %d characters\n", len );  
}  
```  
  
```Output  
wrote 11 characters  
wrote -1 characters  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fprintf、_fprintf_l、fwprintf、_fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf、_scanf_l、wscanf、_wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf、_sscanf_l、swscanf、_swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)