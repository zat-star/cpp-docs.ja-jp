---
title: "sscanf、_sscanf_l、swscanf、_swscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "swscanf"
  - "sscanf"
  - "_sscanf_l"
  - "_swscanf_l"
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
  - "_sscanf_l"
  - "_stscanf"
  - "swscanf"
  - "_stscanf_l"
  - "sscanf"
  - "_swscanf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_sscanf_l 関数"
  - "_stscanf 関数"
  - "_stscanf_l 関数"
  - "_swscanf_l 関数"
  - "読み取り (データを), 文字列"
  - "sscanf 関数"
  - "sscanf_l 関数"
  - "文字列 [C++], 読み取り"
  - "文字列 [C++], 読み取り (データを)"
  - "stscanf 関数"
  - "stscanf_l 関数"
  - "swscanf 関数"
  - "swscanf_l 関数"
ms.assetid: c2dcf0d2-9798-499f-a4a8-06f7e2b9a80c
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# sscanf、_sscanf_l、swscanf、_swscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列から書式付きデータを読み込みます。  これらの関数のセキュリティを強化したバージョンについては、「[sscanf\_s、\_sscanf\_s\_l、swscanf\_s、\_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)」を参照してください。  
  
## 構文  
  
```  
int sscanf(  
   const char *buffer,  
   const char *format [,  
   argument ] ...   
);  
int _sscanf_l(  
   const char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument ] ...   
);  
int swscanf(  
   const wchar_t *buffer,  
   const wchar_t *format [,  
   argument ] ...   
);  
int _swscanf_l(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ] ...   
);  
```  
  
#### パラメーター  
 `buffer`  
 格納されるデータ。  
  
 `format`  
 書式指定文字列。  詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md)」を参照してください。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらの関数は、正常に変換および代入されたフィールドの数を返します。読み込まれただけで代入されなかったフィールドは戻り値には含まれません。  戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。  エラーが発生するか、最初の変換前に文字列の終端に達した場合は `EOF` が返されます。  
  
 `buffer` または `format` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `sscanf` 関数は、各 `argument`で指定された場所に `buffer` からデータを読み込みます。  すべての `argument` は `format`の型指定子に対応する型の変数へのポインターにする必要があります。  引数 `format` は、入力フィールドの解釈を制御し、`scanf` 関数の引数 `format` と同じ形式と機能を持ちます。  重なり合う文字列間でコピーした場合の動作は未定義です。  
  
> [!IMPORTANT]
>  `sscanf` の文字列を読み取るときは、`%s` の書式向けに幅を必ず指定します \(たとえば、`"%s"` の代わりに `"%32s"`\)。それ以外の場合は、不適切な書式を入力するとバッファー オーバーランが発生しやすくなる場合があります。  
  
 `swscanf` は `sscanf` のワイド文字バージョンであり、`swscanf` の引数はワイド文字列です。  `sscanf`はマルチバイトの 16 16 進文字を処理しません。  `swscanf` は Unicode の全角 16 進数または「互換区域」の文字を処理しません。  それ以外では、`swscanf` と `sscanf` の動作は同じです。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_stscanf`|`sscanf`|`sscanf`|`swscanf`|  
|`_stscanf_l`|`_sscanf_l`|`_sscanf_l`|`_swscanf_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`sscanf`, `_sscanf_l`|\<stdio.h\>|  
|`swscanf`, `_swscanf_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_sscanf.c  
// compile with: /W3  
// This program uses sscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  tokenstring[] = "15 12 14...";  
   char  s[81];  
   char  c;  
   int   i;  
   float fp;  
  
   // Input various data from tokenstring:  
   // max 80 character string:  
   sscanf( tokenstring, "%80s", s ); // C4996  
   sscanf( tokenstring, "%c", &c );  // C4996  
   sscanf( tokenstring, "%d", &i );  // C4996  
   sscanf( tokenstring, "%f", &fp ); // C4996  
   // Note: sscanf is deprecated; consider using sscanf_s instead  
  
   // Output the data read  
   printf( "String    = %s\n", s );  
   printf( "Character = %c\n", c );  
   printf( "Integer:  = %d\n", i );  
   printf( "Real:     = %f\n", fp );  
}  
```  
  
  **文字列    \= 15**  
**文字 \= 1**  
**整数:  \= 15**  
**実数:     \= 15.000000**   
## 同等の .NET Framework 関数  
 [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx) などの `Parse` メソッドを参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fscanf、\_fscanf\_l、fwscanf、\_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf、\_scanf\_l、wscanf、\_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [snprintf、\_snprintf、\_snprintf\_l、\_snwprintf、\_snwprintf\_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)