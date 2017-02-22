---
title: "scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wscanf_s"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_scanf_s_l"
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
  - "wscanf_s"
  - "_tscanf_s_l"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_tscanf_s"
  - "_scanf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "入力ストリームからデータ [C++] の読み取り"
  - "バッファ [C++]、バッファー オーバーラン"
  - "_scanf_s_l 関数"
  - "_wscanf_s_l 関数"
  - "tscanf_s_l 関数"
  - "tscanf_s 関数"
  - "scanf_s 関数"
  - "入力ストリームから読み取るデータ [C++]"
  - "wscanf_s 関数"
  - "_tscanf_s_l 関数"
  - "_tscanf_s 関数"
  - "scanf_s_l 関数"
  - "入力ストリームから書式付きデータ [C++]"
  - "wscanf_s_l 関数"
  - "バッファー [C++]、オーバーランの回避"
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

標準入力ストリームから書式付きデータを読み取ります。 これらのバージョンの [scanf、\_scanf\_l、wscanf、\_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) に示すように、セキュリティ拡張機能を持ちます [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)します。  
  
## 構文  
  
```  
int scanf_s(  
   const char *format [,  
   argument]...   
);  
int _scanf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### パラメーター  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 正常に変換され、代入されたフィールドの数を返します。この数には、読み取られても代入されなかったフィールドは含まれません。 戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。 エラーが発生した場合や、まだ文字を読み取っていないときにファイルの終端文字または文字列の終端文字が検出された場合は、`EOF` \(end\-of\-file\) を返します。 場合 `format` は、 `NULL` 」の説明に従って、ポインター、無効なパラメーター ハンドラーが呼び出される [パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、`scanf_s` および `wscanf_s` は `EOF` を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」をご覧ください。  
  
## 解説  
 `scanf_s` 関数は、標準入力ストリーム `stdin` からデータを読み取り、そのデータを `argument` で指定されている位置に書き込みます。 各 `argument` は、`format` の型指定子に対応する型の変数へのポインターにする必要があります。 重なり合う文字列間でコピーした場合の動作は未定義です。  
  
 `wscanf_s` 関数は、`scanf_s` 関数のワイド文字バージョンです。`format` 関数の引数 `wscanf_s` は、ワイド文字列です。 ストリームが ANSI モードで開かれている場合、`wscanf_s` と `scanf_s` の動作は同じになります。`scanf_s` では、UNICODE ストリームからの入力はサポートされていません。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 `scanf` および `wscanf` とは異なり、`scanf_s` および `wscanf_s` では、`c`、`C`、`s`、`S` の各型、または `[]` で囲まれた文字列コントロール セットのすべての入力パラメーターに対してバッファー サイズを指定する必要があります。 バッファー サイズ \(文字単位\) は、バッファーまたは変数のポインターの直後に追加パラメーターとして渡されます。 たとえば、文字列を読み込む場合、その文字列のバッファー サイズは次のように渡されます。  
  
 `char s[10];`  
  
 `scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9`  
  
 バッファー サイズには、終端 null も含まれます。 幅指定フィールドを使用して、読み取られたトークンがバッファーに確実に収まるようにすることができます。 幅指定フィールドが使用されない場合で、読み取られたトークンがバッファーに収まらない場合、そのバッファーには何も書き込まれません。  
  
> [!NOTE]
>  サイズ パラメーターは `unsigned` 型ではなく、`size_t` 型です。 静的キャストを使用して、変換、 `size_t` 値を `unsigned` 64 ビット用の構成をビルドします。  
  
 バッファー サイズ パラメーターで、バイトではなく、文字の最大数を指定する例を次に示します。`wscanf_s` の呼び出しで、バッファーの型により示される文字幅は、書式指定子で示される文字幅に一致していません。  
  
```  
wchar_t ws[10];  
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));  
```  
  
 `S` 書式指定子は、関数がサポートする既定の幅とは "反対" の文字幅の使用を示します。 文字幅は 1 バイトですが、関数は 2 バイト文字をサポートしています。 この例では、最大で 9 つの 1 バイト幅文字の文字列が読み取られ、2 バイト幅文字バッファーに格納されます。 文字は 1 バイト値として処理されます。したがって、最初の 2 文字は `ws[0]` に格納され、次の 2 文字は `ws[1]` に格納され、以降も同様に処理されます。  
  
 文字の場合、次のように 1 文字読み込む場合もあります。  
  
 `char c;`  
  
 `scanf_s("%c", &c, 1);`  
  
 null で終わらない文字列に対して複数の文字列を読み込む場合、幅指定とバッファー サイズとして整数が使用されます。  
  
 `char c[4];`  
  
 `scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 詳細については、「[scanf 関数の文字幅指定](../../c-runtime-library/scanf-width-specification.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tscanf_s`|`scanf_s`|`scanf_s`|`wscanf_s`|  
|`_tscanf_s_l`|`_scanf_s_l`|`_scanf_s_l`|`_wscanf_s_l`|  
  
 詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`scanf_s`, `_scanf_s_l`|\<stdio.h\>|  
|`wscanf_s`, `_wscanf_s_l`|\<stdio.h\> または \<wchar.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。 コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 使用例  
  
```  
// crt_scanf_s.c  
// This program uses the scanf_s and wscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int      i,  
            result;  
   float    fp;  
   char     c,  
            s[80];  
   wchar_t  wc,  
            ws[80];  
  
   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,  
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,  
           wc, s, ws);  
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   wprintf( L"The number of fields input is %d\n", result );  
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,  
            c, wc, s, ws);  
}  
```  
  
 この入力を使用すると、このプログラムでは次の出力が生成されます。  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
```Output  
フィールドの入力数は 6 の内容: 71 98.599998 h z がバイト文字の入力フィールドの数は 6 の内容: 36 92.300003 y n ワイド文字  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
-   [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)  
  
-   関連項目 `Parse` メソッドなど、 [:parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)します。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [fscanf、\_fscanf\_l、fwscanf、\_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf、\_sscanf\_l、swscanf、\_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)