---
title: "ungetc、ungetwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ungetwc"
  - "ungetc"
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
  - "_ungettc"
  - "ungetwc"
  - "ungetc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ungettc 関数"
  - "文字, 戻す (ストリームに)"
  - "ungetc 関数"
  - "ungettc 関数"
  - "ungetwc 関数"
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# ungetc、ungetwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームに文字をプッシュ バックします。  
  
## 構文  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### パラメーター  
 `c`  
 プッシュする文字。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 正常に終了した場合、これらの各関数は文字引数 `c` を返します。`c` がプッシュ バックできない場合、または文字が読まれなかった場合は、入力ストリームは変更されず、`ungetc` は `EOF` を返します。`ungetwc` は、`WEOF` を返します。  `stream` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`EOF` または `WEOF` が返され、`errno` が `EINVAL` に設定されます。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `ungetc` 関数は `stream` に文字 `c` をプッシュ バックし、EOF インジケーターをクリアします。  ストリームは、読み取り用に開かれている必要があります。  `stream` の後続の読み取り操作は、`c` から始まります。`ungetc` を使用してストリームに `EOF` をプッシュする操作は無視されます。  
  
 `ungetc` がストリームに入れた文字は、その文字をストリームから読み取る前に `fflush`、`fseek`、`fsetpos`、または `rewind` が呼び出されると削除されることがあります。  ファイル位置インジケーターの値は、文字がプッシュ バックされる前のファイル位置インジケーターの値になります。  ストリームに対応する外部のストレージは変更されません。  テキスト ストリームに対する `ungetc` の正常な呼び出しでは、プッシュ バックされたすべての文字が読み取りまたは破棄されるまで、ファイル位置インジケーターは未指定です。  バイナリ ストリームに対する `ungetc` の正常な呼び出しでは、ファイル位置インジケーターがデクリメントされます。呼び出し前の値が 0 の場合、呼び出しの後の値は未定義です。  
  
 `ungetc` を 2 回の呼び出したときに、呼び出しの間に読み取りまたはファイル位置の操作をしなかった場合は、結果は予測できません。  `fscanf` の呼び出し後に、他の読み取り操作 \(`getc` など\) が行われない場合は、`ungetc` の呼び出しが失敗する可能性があります。  これは `fscanf` 自体が `ungetc` を呼び出すためです。  
  
 `ungetwc` 関数は、`ungetc` 関数のワイド文字バージョンです。  しかし、テキスト ストリームまたはバイナリ ストリームに対する `ungetwc` の正常な呼び出しでは、プッシュ バックされたすべての文字が読み取りまたは破棄されるまで、ファイル位置インジケーターの値は未指定です。  
  
 これらの関数はスレッド セーフであり、実行時に重要情報をロックします。  ロックしないバージョンについては、「[\_ungetc\_nolock、\_ungetwc\_nolock](../Topic/_ungetc_nolock,%20_ungetwc_nolock.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`ungetc`|\<stdio.h\>|  
|`ungetwc`|\<stdio.h\> または \<wchar.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
  **`521a`番号 \= 521**  
**ストリームの次の文字 \= 'a'**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [getc、getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc、putwc](../../c-runtime-library/reference/putc-putwc.md)