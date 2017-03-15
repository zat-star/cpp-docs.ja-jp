---
title: "vsnprintf、_vsnprintf、_vsnprintf_l、_vsnwprintf、_vsnwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vsnprintf"
  - "_vsnprintf_l"
  - "_vsnwprintf"
  - "_vsnwprintf_l"
  - "_vsnprintf"
  - "_vsnprintf;"
  - "vsnprintf; _vsnprintf"
  - "_vsnwprintf;"
  - "_vsnprintf_l;"
  - "_vsnwprintf_l;"
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
  - "ntoskrnl.exe"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_vsnprintf"
  - "_vsnwprintf"
  - "_vsntprintf"
  - "vsnprintf"
  - "stdio/vsnprintf"
  - "stdio/_vsnprintf"
  - "stdio/_vsnprintf_l"
  - "stdio/_vsnwprintf"
  - "stdio/_vsnwprintf_l"
  - "_vsnprintf_l"
  - "_vsnwprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vsntprintf 関数"
  - "_vsnwprintf_l 関数"
  - "vsnwprintf_l 関数"
  - "vsntprintf_l 関数"
  - "_vsntprintf 関数"
  - "_vsnprintf_l 関数"
  - "vsnprintf 関数"
  - "_vsntprintf_l 関数"
  - "vsnprintf_l 関数"
  - "_vsnwprintf 関数"
  - "_vsnprintf 関数"
  - "書式設定テキスト [C++]"
  - "vsnwprintf 関数"
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
caps.latest.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 35
---
# vsnprintf、_vsnprintf、_vsnprintf_l、_vsnwprintf、_vsnwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数リストへのポインターを使用して、書式付き出力を書き込みます。 これらの関数のセキュリティを強化したバージョンを使用できます。「[vsnprintf\_s、\_vsnprintf\_s、\_vsnprintf\_s\_l、\_vsnwprintf\_s、\_vsnwprintf\_s\_l](../../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)」をご覧ください。  
  
## 構文  
  
```  
int vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_l(  
   char *buffer,  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vsnwprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vsnwprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf_l(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf_l(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
```  
  
#### パラメーター  
 `buffer`  
 出力の格納位置。  
  
 `count`  
 書き込む最大文字数。  
  
 `format`  
 書式の指定。  
  
 `argptr`  
 引数リストへのポインター。  
  
 `locale`  
 使用するロケール。  
  
 詳細については、「[printf 関数と wprintf 関数の書式指定フィールド](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)」を参照してください。  
  
## 戻り値  
 `vsnprintf` 関数は、終端の null 文字をカウントせずに書き込まれた文字数を返します。 バッファーのサイズが指定された場合 `count` で指定された出力を格納する十分な大きさがない `format` と `argptr`, の戻り値 `vsnprintf` 記述がいない場合は null 文字をカウントする文字の数は、 `count` が十分な大きさです。 戻り値がより大きい場合 `count` \- 1 の場合、出力が切り捨てられました。 戻り値 \-1 は、エンコード エラーが発生したことを示します。  
  
 両方 `_vsnprintf` と `_vsnwprintf` かどうかに書き込む文字数は、以下に書き込まれた文字数を返す `count`に書き込む文字数がより大きい場合、 `count`, 、これら関数の出力が切り捨てられたことを示す\-1 を返します。  
  
 これらすべての関数によって返される値ではない、またはいずれかが書き込まれるかどうか、終端の null は含まれません。`count` が 0 の場合は、関数、書き込み、文字数を含む、終端の null 値が返されます。 この結果、文字列とその終端の null を割り当てるための十分なバッファー領域を使用して、バッファーが満杯にもう一度関数を呼び出すことができます。  
  
 場合 `format` は `NULL`, 、または `buffer` null と `count` は 0 に等しい、これらの関数、無効なパラメーター ハンドラーを呼び出します」の説明に従って [パラメーターの検証](../../c-runtime-library/parameter-validation.md)します。 実行の継続が許可された場合、これらの関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
## 解説  
 これらの各関数は、引数リストへのポインターを取り、データを書式指定して、`count` 文字数までの文字を `buffer` が指すメモリに書き込みます。`vsnprintf` 関数は、出力が切り捨てられる場合でも常に null 終端記号を書き込みます。`_vsnprintf` と `_vsnwprintf` を使用するときは、終端に空きがある場合 \(つまり、書き込む文字数が `count` 未満の場合\) に限り、バッファーは null で終わります。  
  
> [!IMPORTANT]
>  特定の種類のセキュリティ リスクを防ぐため、`format` がユーザー定義の文字列ではないことを確認してください。 詳しくは、「[バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
> [!NOTE]
>  `_vsnprintf`、`_vsnprintf_l`、`_vsnwprintf`、`_vsnwprintf_l` を呼び出すときに、終端の null 用の空きを確保するために、`count` を必ずバッファー長未満にし、この関数を呼び出す前にバッファーを null に初期化してください。  
>   
>  `vsnprintf` 終端の null を常に書き込み、 `count` パラメーター バッファーのサイズに等しい場合があります。  
  
 Visual Studio 2015 および Windows 10 で UCRT と共に開始する場合、`vsnprintf` は `_vsnprintf` と同一ではなくなります。`vsnprintf` 関数は C99 標準に準拠している `_vnsprintf` 以前の Visual Studio コードとの下位互換性は保持されます。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_vsntprintf`|`_vsnprintf`|`_vsnprintf`|`_vsnwprintf`|  
|`_vsntprintf_l`|`_vsnprintf_l`|`_vsnprintf_l`|`_vsnwprintf_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー \(C\)|必須ヘッダー \(C\+\+\)|  
|----------|------------------|----------------------|  
|`vsnprintf`、`_vsnprintf`、`_vsnprintf_l`|\<stdio.h\>|\<stdio.h\> または \<cstdio\>|  
|`_vsnwprintf`, `_vsnwprintf_l`|\<stdio.h\> または \<wchar.h\>|\<stdio.h\>、\<wchar.h\>、\<cstdio\>、または \<cwchar\>|  
  
 `_vsnprintf`、`_vsnprintf_l`、`_vsnwprintf`、`_vsnwprintf_l` の各関数は、Microsoft 固有の関数です。 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```c  
// crt_vsnwprintf.c  
// compile by using: cl /W3 crt_vsnwprintf.c  
  
// To turn off error C4996, define this symbol:  
#define _CRT_SECURE_NO_WARNINGS  
  
#include <stdio.h>  
#include <wtypes.h>  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(LPCWSTR formatstring, ...)  
{  
    int nSize = 0;  
    wchar_t buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead  
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996  
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);  
}  
  
int main() {  
    FormatOutput(L"%ls %ls", L"Hi", L"there");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");  
}  
```  
  
```Output  
nSize: 8、ファン: Hi が nSize: 9、ファン: Hi あります!nSize:-1、ファン: Hi があります。  
```  
  
 Vsnprintf を代わりに、ナロー文字列のパラメーターと共に使用すると、動作が変更されます。`count` パラメーターは、バッファーの全体サイズを指定でき、戻り値は、書き込まれている場合は文字数 `count` が十分で。  
  
## 使用例  
  
```c  
// crt_vsnprintf.c  
// compile by using: cl /W4 crt_vsnprintf.c  
#include <stdio.h>  
#include <stdarg.h> // for va_list, va_start  
#include <string.h> // for memset  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(char* formatstring, ...)  
{  
    int nSize = 0;  
    char buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);  
    printf("nSize: %d, buff: %s\n", nSize, buff);  
}  
  
int main() {  
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null  
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null  
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null  
}  
```  
  
```Output  
nSize: 8、ファン: Hi が nSize: 9、ファン: Hi あります!nSize: 10、ファン: Hi があります。  
```  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [書式指定構文: printf 関数と wprintf 関数](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg、va\_copy、va\_end、va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)