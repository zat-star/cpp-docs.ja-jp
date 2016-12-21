---
title: "gets_s、_getws_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getws_s"
  - "gets_s"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getws_s"
  - "gets_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getws_s 関数"
  - "バッファー オーバーラン"
  - "バッファー, 回避 (オーバーランの)"
  - "バッファー, バッファー オーバーラン"
  - "gets_s 関数"
  - "getws_s 関数"
  - "線, 取得"
  - "標準入力, 読み取り"
  - "ストリーム, 取得 (行を)"
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
caps.latest.revision: 29
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gets_s、_getws_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`stdin` ストリームから行を取得します。  「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[gets、\_getws](../../c-runtime-library/gets-getws.md) のこれらのバージョンではセキュリティが強化されています。  
  
## 構文  
  
```  
char *gets_s(   
   char *buffer,  
   size_t sizeInCharacters  
);  
wchar_t *_getws_s(   
   wchar_t *buffer,  
   size_t sizeInCharacters  
);  
template <size_t size>  
char *gets_s(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws_s(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### パラメーター  
 \[出力\] `buffer`  
 入力文字列の格納場所。  
  
 \[入力\] `sizeInCharacters`  
 バッファーのサイズ。  
  
## 戻り値  
 正常に終了した場合は `buffer` を返します。  エラーが発生した場合またはファイルの終端に達した場合は、`NULL` ポインターを返します。  どちらが発生したかを確認するには、[ferror](../../c-runtime-library/reference/ferror.md) または [feof](../../c-runtime-library/reference/feof.md) を使用します。  
  
## 解説  
 `gets_s` 関数は、`stdin` 標準入力ストリームから行を読み取り、`buffer` に格納します。  行は、最初の改行文字 \('\\n'\) までのすべての文字 \(改行文字を含む\) で構成されます。  `gets_s` は、行を返す前に、改行文字を null 文字 \('\\0'\) に置き換えます。  これとは対照的に、`fgets_s` 関数は改行文字を保持します。  
  
 最初に読み取られた文字がファイルの終端の文字である場合、null 文字が `buffer` の先頭に格納され、`NULL` が返されます。  
  
 ワイド文字を扱う場合は、`gets_s` ではなく `_getws` を使用します。引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  
  
 `buffer` が `NULL` の場合、`sizeInCharacters` が 0 以下の場合、またはバッファーが小さすぎて入力行と終端の null を格納できない場合、これらの関数は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `NULL` を返し、errno を `ERANGE` に設定します。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_getts`|`gets_s`|`gets_s`|`_getws`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`gets_s`|\<stdio.h\>|  
|`_getws`|\<stdio.h\> または \<wchar.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_gets_s.c  
// This program retrieves a string from the stdin and   
// prints the same string to the console.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets_s( line, 20 );  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
  **`Hello there!`入力された行: Hello there\!**   
## 同等の .NET Framework 関数  
 [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [gets、\_getws](../../c-runtime-library/gets-getws.md)   
 [fgets、fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs、fputws](../Topic/fputs,%20fputws.md)   
 [puts、\_putws](../Topic/puts,%20_putws.md)