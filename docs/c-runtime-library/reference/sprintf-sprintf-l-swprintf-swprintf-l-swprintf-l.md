---
title: "sprintf、_sprintf_l、swprintf、_swprintf_l、__swprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__swprintf_l"
  - "sprintf"
  - "_sprintf_l"
  - "_swprintf_l"
  - "swprintf"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_stprintf_l"
  - "__swprintf_l"
  - "sprintf_l"
  - "swprintf"
  - "_sprintf_l"
  - "sprintf"
  - "_stprintf"
  - "stprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__swprintf_l 関数"
  - "_CRT_NON_CONFORMING_SWPRINTFS"
  - "_sprintf_l 関数"
  - "_stprintf 関数"
  - "_stprintf_l 関数"
  - "_swprintf_l 関数"
  - "書式設定テキスト [C++]"
  - "sprintf 関数"
  - "sprintf_l 関数"
  - "stprintf 関数"
  - "stprintf_l 関数"
  - "文字列 [C++], 書き込み"
  - "swprintf 関数"
  - "swprintf_l 関数"
ms.assetid: f6efe66f-3563-4c74-9455-5411ed939b81
caps.latest.revision: 36
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 36
---
# sprintf、_sprintf_l、swprintf、_swprintf_l、__swprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列に書式付きデータを書き込みます。  これらの関数のセキュリティを強化したバージョンについては、「[sprintf\_s、\_sprintf\_s\_l、swprintf\_s、\_swprintf\_s\_l](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)」を参照してください。  セキュリティを強化したバージョンの `swprintf` と `_swprintf_l` は、`count` パラメーターを受け取りません。  
  
## 構文  
  
```  
int sprintf(  
   char *buffer,  
   const char *format [,  
   argument] ...   
);  
int _sprintf_l(  
   char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int swprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format [,  
   argument]...  
);  
int _swprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
int __swprintf_l(  
   wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int sprintf(  
   char (&buffer)[size],  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _sprintf_l(  
   char (&buffer)[size],  
   const char *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
  
```  
  
#### パラメーター  
 `buffer`  
 出力の格納場所。  
  
 `count`  
 この関数の Unicode バージョンで格納する最大文字数。  
  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
 詳細については、「[printf 関数と wprintf 関数の書式指定フィールド](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)」を参照してください。  
  
## 戻り値  
 書き込まれた文字数を返します。エラーが発生した場合は \-1 を返します。  `buffer` または `format` が null ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
 `sprintf` 関数は、`buffer` に格納されているバイト数を返します。終端の null 文字は含まれません。  `swprintf`関数は、`buffer` に格納されているワイド文字数を返します。終端の null 文字は含まれません。  
  
## 解説  
 `sprintf` 関数は、一連の文字と値の書式を指定して、`buffer` に格納します。  各 `argument` \(指定されている場合\) は、`format` 中の対応する書式指定に応じて変換され、格納されます。  format は通常の文字で構成し、その形式と機能は `format`printf 関数の [と同じです。](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 最後に書き込まれる文字の後に NULL 文字が追加されます。  重なり合う文字列間でコピーした場合の動作は未定義です。  
  
> [!IMPORTANT]
>  `sprintf` 関数を使用する際、書き込まれる文字数は制限できないため、`sprintf` 関数を使用しているコードでは、バッファー オーバーランが発生しやすくなります。  関連する関数である [\_snprintf](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) の使用を検討してください。この関数では、`buffer` に書き込まれる最大文字数を指定できます。[\_scprintf](../Topic/_scprintf,%20_scprintf_l,%20_scwprintf,%20_scwprintf_l.md) を使用すると、必要なバッファーのサイズを調べることができます。  また、`format` にユーザー定義の文字列を指定しないでください。  
  
 `swprintf` は `sprintf` のワイド文字バージョンであり、`swprintf` のポインター引数はワイド文字列です。  `swprintf` と `sprintf` では、エンコーディング エラーの検出動作が異なる場合があります。  `swprintf` と `fwprintf` の動作は同じですが、`swprintf` は `FILE` 型の出力先ではなく文字列に出力を書き込む点と、`swprintf` には書き込む最大文字数を指定する `count` パラメーターが必要である点が異なります。  これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 `swprintf` 関数は ISO C 規格に準拠しています。この規格では、2 番目のパラメーター `count` を `size_t` 型で指定する必要があります。  古い非標準の動作を強制的に実行させるには、`_CRT_NON_CONFORMING_SWPRINTFS` を定義します。  この古い動作は、将来的には削除される可能性があるので、規格に準拠した新しい動作を使用するようにコードを変更する必要があります。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_stprintf`|`sprintf`|`sprintf`|`_swprintf`|  
|`_stprintf_l`|`_sprintf_l`|`_sprintf_l`|`__swprintf_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`sprintf`, `_sprintf_l`|\<stdio.h\>|  
|`swprintf`, `_swprintf_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_sprintf.c  
// compile with: /W3  
// This program uses sprintf to format various  
// data and place them in the string named buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf( buffer,     "   String:    %s\n", s ); // C4996  
   j += sprintf( buffer + j, "   Character: %c\n", c ); // C4996  
   j += sprintf( buffer + j, "   Integer:   %d\n", i ); // C4996  
   j += sprintf( buffer + j, "   Real:      %f\n", fp );// C4996  
   // Note: sprintf is deprecated; consider using sprintf_s instead  
  
   printf( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
}  
```  
  
  **Output:**  
 **String:    computer**  
 **Character: l**  
 **Integer:   35**  
 **Real:      1.732053**  
**character count \= 79**   
## 使用例  
  
```  
// crt_swprintf.c  
// wide character example  
// also demonstrates swprintf returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf fails because string contains WEOF (\xffff)  
   printf( "wrote %d characters\n", len );  
}  
```  
  
  **wrote 11 characters**  
**wrote \-1 characters**   
## 同等の .NET Framework 関数  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf、\_scanf\_l、wscanf、\_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf、\_sscanf\_l、swscanf、\_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)