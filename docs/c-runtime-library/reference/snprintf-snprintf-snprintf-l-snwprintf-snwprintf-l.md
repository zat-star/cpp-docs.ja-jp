---
title: "snprintf、_snprintf、_snprintf_l、_snwprintf、_snwprintf_l | Microsoft Docs"
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
  - "_snwprintf"
  - "_snprintf"
  - "_snprintf_l"
  - "_snwprintf_l"
  - "snprintf"
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
  - "_snprintf"
  - "snprintf_l"
  - "snwprintf_l"
  - "sntprintf"
  - "snprintf"
  - "_sntprintf"
  - "_sntprintf_l"
  - "sntprintf_l"
  - "snwprintf"
  - "_snprintf_l"
  - "_snwprintf"
  - "_snwprintf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "snwprintf_l 関数"
  - "sntprintf_l 関数"
  - "snprintf_l 関数"
  - "_snwprintf_l 関数"
  - "_sntprintf_l 関数"
  - "_snwprintf 関数"
  - "_snprintf 関数"
  - "_sntprintf 関数"
  - "_snprintf_l 関数"
  - "snwprintf 関数"
  - "snprintf 関数"
  - "sntprintf 関数"
  - "書式設定テキスト [C++]"
ms.assetid: 5976c9c8-876e-4ac9-a515-39f3f7fd0925
caps.latest.revision: 35
caps.handback.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# snprintf、_snprintf、_snprintf_l、_snwprintf、_snwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列に書式付きデータを書き込みます。 これらの関数のセキュリティを強化したバージョンを使用できます。「[\_snprintf\_s、\_snprintf\_s\_l、\_snwprintf\_s、\_snwprintf\_s\_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)」をご覧ください。  
  
## 構文  
  
```  
int snprintf(  
   char *buffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf(  
   char *buffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf_l(  
   char *buffer,  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _snwprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
);  
int _snwprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int _snprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snprintf_l(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf_l(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
```  
  
#### パラメーター  
 `buffer`  
 出力の格納場所。  
  
 `count`  
 格納する最大文字数。  
  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
 詳細については、「[書式指定構文: printf 関数と wprintf 関数](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)」を参照してください。  
  
## 戻り値  
 以下の説明では、書式付きデータ文字列の長さ \(終端の null は含まない\) を `len` とします。`len` と `count` は、`snprintf` 関数と `_snprintf` 関数ではバイト単位、`_snwprintf` 関数ではワイド文字単位になります。  
  
 すべての関数について、`len` \< `count` の場合、`len` の文字数が `buffer` に格納されて、終端の null が追加され、`len` が返されます。  
  
 `snprintf` 関数は、`len` が `count` 以上の場合、null 終端記号を `buffer[count-1]` に配置することによって、出力を切り捨てます。 戻り値は `len` です。`count` のサイズが十分な場合に出力されたであろう文字数です。`snprintf` 関数は、エンコード エラーが発生すると負の値を返します。  
  
 `snprintf` を除くすべての関数について、`len` \= `count` の場合、`len` の文字数が `buffer` に格納されて、終端の null は追加されず、`len` が返されます。`len` \> `count` の場合、`count` の文字数が `buffer` に格納されて、終端の null は追加されずに、負の値が返されます。  
  
 `buffer` が null ポインターで `count` がゼロの場合、`len` は、出力の書式を指定するのに必要な文字数として返されます。終端の null は含まれません。 同じ `argument` パラメーターおよび `locale` パラメーターを指定して正常な呼び出しを行うには、少なくとも `len` \+ 1 文字を保持するバッファーを割り当てます。  
  
 `buffer` が null ポインターで `count` が 0 以外の場合、または `format` が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、正しくないパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」をご覧ください。  
  
## 解説  
 `snprintf` 関数と、関数の `_snprintf` ファミリは、`count` 以下の文字数を書式指定し、`buffer` に格納します。`snprintf` 関数は、常に終端の null 文字を格納し、必要に応じて出力を切り捨てます。 関数の `_snprintf` ファミリは、書式付き文字列の長さが確実に `count` 文字数未満の場合にのみ、終端の null 文字を追加します。 各 `argument` \(指定されている場合\) は、`format` 中の対応する書式指定に応じて変換され、格納されます。 format は通常の文字で構成し、その形式と機能は [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 関数の `format` と同じです。 重なり合う文字列間でコピーした場合の動作は未定義です。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。`_snprintf` 関数では NULL で終わることが保証されないため \(特に戻り値が `count` の場合\)、これらの関数の後に、終端の null を追加するコードが続いていることを確認してください。 詳しくは、「[バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
 Visual Studio 2015 および Windows 10 で UCRT と共に開始する場合、`snprintf` は `_snprintf` と同一ではなくなります。`snprintf` 関数の動作は、現在 C99 標準準拠です。  
  
 `_snwprintf` は `_snprintf` のワイド文字バージョンであり、`_snwprintf` のポインター引数はワイド文字列です。`_snwprintf` と `_snprintf` では、エンコーディング エラーの検出動作が異なる場合があります。`_snwprintf` と同様に、`swprintf` では出力が `FILE` 型の出力先ではなく文字列に書き込まれます。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、より安全な新しいバージョンを呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_sntprintf`|`_snprintf`|`_snprintf`|`_snwprintf`|  
|`_sntprintf_l`|`_snprintf_l`|`_snprintf_l`|`_snwprintf_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`snprintf`、`_snprintf`、 `_snprintf_l`|\<stdio.h\>|  
|`_snwprintf`, `_snwprintf_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 使用例  
  
```c  
// crt_snprintf.c  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
#if !defined(__cplusplus)  
typedef int bool;  
const bool true = 1;  
const bool false = 0;  
#endif  
  
#define FAIL 0 // change to 1 and see what happens  
  
int main(void)  
{  
   char buffer[200];  
   const static char s[] = "computer"  
#if FAIL  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
#endif  
   ;  
   const char c = 'l';   
   const int i = 35;  
#if FAIL  
   const double fp = 1e300; // doesn't fit in the buffer  
#else  
   const double fp = 1.7320534;  
#endif  
   /* !subtract one to prevent "squeezing out" the terminal nul! */  
   const int bufferSize = sizeof(buffer)/sizeof(buffer[0]) - 1;  
   int bufferUsed = 0;  
   int bufferLeft = bufferSize - bufferUsed;  
   bool bSuccess = true;  
   buffer[0] = 0;  
  
   /* Format and print various data: */  
  
   if (bufferLeft > 0)  
   {  
      int perElementBufferUsed = _snprintf(&buffer[bufferUsed],   
      bufferLeft, "   String: %s\n", s ); // C4996  
      // Note: _snprintf is deprecated; consider _snprintf_s instead  
      if (bSuccess = (perElementBufferUsed >= 0))  
      {  
         bufferUsed += perElementBufferUsed;  
         bufferLeft -= perElementBufferUsed;  
         if (bufferLeft > 0)  
         {  
            int perElementBufferUsed = _snprintf(&buffer[bufferUsed],   
            bufferLeft, "   Character: %c\n", c ); // C4996  
            if (bSuccess = (perElementBufferUsed >= 0))  
            {  
               bufferUsed += perElementBufferUsed;  
               bufferLeft -= perElementBufferUsed;  
               if (bufferLeft > 0)  
               {  
                  int perElementBufferUsed = _snprintf(&buffer  
                  [bufferUsed], bufferLeft, "   Integer: %d\n", i ); // C4996  
                  if (bSuccess = (perElementBufferUsed >= 0))  
                  {  
                     bufferUsed += perElementBufferUsed;  
                     bufferLeft -= perElementBufferUsed;  
                     if (bufferLeft > 0)  
                     {  
                        int perElementBufferUsed = _snprintf(&buffer  
                        [bufferUsed], bufferLeft, "   Real: %f\n", fp ); // C4996  
                        if (bSuccess = (perElementBufferUsed >= 0))  
                        {  
                           bufferUsed += perElementBufferUsed;  
                        }  
                     }  
                  }  
               }  
            }  
         }  
      }  
   }  
  
   if (!bSuccess)  
   {  
      printf("%s\n", "failure");  
   }  
   else  
   {  
      /* !store nul because _snprintf doesn't necessarily (if the string   
       * fits without the terminal nul, but not with it)!  
       * bufferUsed might be as large as bufferSize, which normally is   
       * like going one element beyond a buffer, but in this case   
       * subtracted one from bufferSize, so we're ok.  
       */  
      buffer[bufferUsed] = 0;  
      printf( "Output:\n%s\ncharacter count = %d\n", buffer, bufferUsed );  
   }  
   return EXIT_SUCCESS;  
}  
```  
  
```Output  
Output: String: computer Character: l Integer: 35 Real: 1.732053 character count = 69  
```  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf、\_scanf\_l、wscanf、\_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf、\_sscanf\_l、swscanf、\_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)