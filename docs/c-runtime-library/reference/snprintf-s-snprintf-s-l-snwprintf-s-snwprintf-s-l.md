---
title: "_snprintf_s、_snprintf_s_l、_snwprintf_s、_snwprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_snprintf_s"
  - "_snprintf_s_l"
  - "_snwprintf_s"
  - "_snwprintf_s_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "_snwprintf_s_l"
  - "_sntprintf_s_l"
  - "snprintf_s_l"
  - "_snprintf_s_l"
  - "_sntprintf_s"
  - "_snprintf_s"
  - "snprintf_s"
  - "_snwprintf_s"
  - "snwprintf_s_l"
  - "snwprintf_s"
  - "sntprintf_s"
  - "sntprintf_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_snprintf_s 関数"
  - "_snprintf_s_l 関数"
  - "_sntprintf_s 関数"
  - "_sntprintf_s_l 関数"
  - "_snwprintf_s 関数"
  - "_snwprintf_s_l 関数"
  - "書式設定テキスト [C++]"
  - "snprintf_s 関数"
  - "snprintf_s_l 関数"
  - "sntprintf_s 関数"
  - "sntprintf_s_l 関数"
  - "snwprintf_s 関数"
  - "snwprintf_s_l 関数"
ms.assetid: 9336ab86-13e5-4a29-a3cd-074adfee6891
caps.latest.revision: 32
caps.handback.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _snprintf_s、_snprintf_s_l、_snwprintf_s、_snwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列に書式付きデータを書き込みます。 これらのバージョンは、 [snprintf、\_snprintf、\_snprintf\_l、\_snwprintf、\_snwprintf\_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) 」の説明に従って、セキュリティ強化機能を備えた [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)します。  
  
## 構文  
  
```  
int _snprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _snwprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
);  
int _snwprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int _snprintf_s(  
   char (&buffer)[size],  
   size_t count,  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf_s(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
); // C++ only  
```  
  
#### パラメーター  
 `buffer`  
 出力の格納場所。  
  
 `sizeOfBuffer`  
 出力の格納場所のサイズ。 サイズで `bytes` の `_snprintf_s` サイズまたは `words` の `_snwprintf_s`です。  
  
 `Count`  
 格納するには文字の最大数または [\_TRUNCATE](../../c-runtime-library/truncate.md)です。  
  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `_snprintf_s` 格納されている文字数を返します `buffer`, 、終端の null 文字をカウントしません。`_snwprintf_s` 格納されるワイド文字の数を返します `buffer`, 、終端の null ワイド文字をカウントしません。  
  
 データと終端の null を格納するために必要な記憶域を超えた場合 `sizeOfBuffer`, 、」の説明に従って、無効なパラメーター ハンドラーが呼び出される [パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 無効なパラメーター ハンドラーの後に実行が継続されると、これらの関数は `buffer` を空の文字列に、`errno` を `ERANGE` に設定し、\-1 を返します。  
  
 `buffer` または `format` が `NULL` ポインターの場合、または `count` が 0 以下の場合は、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、\-1 を返します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_snprintf_s` 関数の形式とストア `count` または文字の数が少ない `buffer` 終端の null を追加します。 各引数 \(指定されている場合\) が変換されに対応する書式指定に応じて `format`します。 一貫した書式設定は、 `printf` 関数のファミリ; を参照してください [書式指定構文: printf 関数と wprintf 関数](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)します。 重なり合う文字列間でコピーした場合の動作は未定義です。  
  
 場合 `count` は [\_TRUNCATE](../../c-runtime-library/truncate.md), 、し `_snprintf_s` だけだけでなく、文字列の書き込み合わせて `buffer` 、終端の null の領域を確保したままです。 内に収まる範囲、文字列全体 \(終端の null\) 場合 `buffer`, 、し `_snprintf_s` 、文字数を返します \(終端の null は含まない\) に書き込まれます。 それ以外の場合、 `_snprintf_s` 場合、\-1 を切り捨てが発生したを返します。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  
  
 `_snwprintf_s` は `_snprintf_s` のワイド文字バージョンであり、`_snwprintf_s` のポインター引数はワイド文字列です。`_snwprintf_s` と `_snprintf_s` では、エンコーディング エラーの検出動作が異なる場合があります。`_snwprintf_s`, 、のような `swprintf_s`, 、型の出力先ではなく、文字列に出力を書き込みます `FILE`します。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_sntprintf_s`|`_snprintf_s`|`_snprintf_s`|`_snwprintf_s`|  
|`_sntprintf_s_l`|`_snprintf_s_l`|`_snprintf_s_l`|`_snwprintf_s_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_snprintf_s`, `_snprintf_s_l`|\<stdio.h\>|  
|`_snwprintf_s`, `_snwprintf_s_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_snprintf_s.cpp  
// compile with: /MTd  
  
// These #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
int snprintf_s_tester( const char * fmt, int x, size_t count )  
{  
   char dest[10];  
  
   printf( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf( "%zd-byte buffer; truncation semantics\n",  
               _countof(dest) );  
   else  
      printf( "count = %zd; %zd-byte buffer\n",  
               count, _countof(dest) );  
  
   int ret = _snprintf_s( dest, _countof(dest), count, fmt, x );  
  
   printf( "    new contents of dest: '%s'\n", dest );  
  
   return ret;  
}  
  
void Examples()  
{  
   // formatted output string is 9 characters long: "<<<123>>>"  
   snprintf_s_tester( "<<<%d>>>", 121, 8 );  
   snprintf_s_tester( "<<<%d>>>", 121, 9 );  
   snprintf_s_tester( "<<<%d>>>", 121, 10 );  
  
   printf( "\nDestination buffer too small:\n" );  
  
   snprintf_s_tester( "<<<%d>>>", 1221, 10 );  
  
   printf( "\nTruncation examples:\n" );  
  
   int ret = snprintf_s_tester( "<<<%d>>>", 1221, _TRUNCATE );  
   printf( "    truncation %s occur\n", ret == -1 ? "did"  
                                                  : "did not" );  
  
   ret = snprintf_s_tester( "<<<%d>>>", 121, _TRUNCATE );  
   printf( "    truncation %s occur\n", ret == -1 ? "did"  
                                                  : "did not" );  
   printf( "\nSecure template overload example:\n" );  
  
   char dest[10];  
   _snprintf( dest, 10, "<<<%d>>>", 12321 );  
   // With secure template overloads enabled (see #defines  
   // at top of file), the preceding line is replaced by  
   //    _snprintf_s( dest, _countof(dest), 10, "<<<%d>>>", 12345 );  
   // Instead of causing a buffer overrun, _snprintf_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, _snprintf would  
   // write 10 characters and overrun the dest buffer.  
   printf( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter handler invoked: %s\n", expression);  
}  
  
int main( void )  
{  
   _invalid_parameter_handler oldHandler, newHandler;  
  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   Examples();  
}  
```  
  
```Output  
  
count = 8 です。追加先の 10 バイトのバッファーの新しい内容: '<<< 121 >>' 数 = 9 です。追加先の 10 バイトのバッファーの新しい内容: '<<< 121 >>> ' のカウント = 10 です。追加先の 10 バイトのバッファーの新しい内容: '<<< 121 >>> ' のターゲット バッファーが小さすぎます: カウント = 10 の範囲10 バイト バッファー無効なパラメーター ハンドラーが呼び出されました: ("バッファーが小さすぎます"、0) 追加先の新しい内容: ' 切り捨ての例: 10 バイト バッファーです。切り捨てセマンティクスの追加先の新しい内容: '<<< 1221 >>' 10 バイト バッファーに切り捨てが発生しました切り捨てセマンティクスの追加先の新しい内容: '<<< 121 >>> ' の切り捨てが発生しなかったセキュリティで保護されたテンプレート オーバー ロードの例: 無効なパラメーター ハンドラーが呼び出されました: ("バッファーが小さすぎます"、0) 追加先の新しい内容: '  
```  
  
## 同等の .NET Framework 関数  
 該当しない。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf、\_scanf\_l、wscanf、\_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf、\_sscanf\_l、swscanf、\_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)