---
title: "vsnprintf、_vsnprintf、_vsnprintf_l、_vsnwprintf、_vsnwprintf_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _vsnprintf
- _vsnprintf_l
- _vsnwprintf
- _vsnwprintf_l
- _vsnprintf
- _vsnprintf;
- vsnprintf; _vsnprintf
- _vsnwprintf;
- _vsnprintf_l;
- _vsnwprintf_l;
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vsnprintf
- _vsnwprintf
- _vsntprintf
- vsnprintf
- stdio/vsnprintf
- stdio/_vsnprintf
- stdio/_vsnprintf_l
- stdio/_vsnwprintf
- stdio/_vsnwprintf_l
- _vsnprintf_l
- _vsnwprintf_l
dev_langs: C++
helpviewer_keywords:
- vsntprintf function
- _vsnwprintf_l function
- vsnwprintf_l function
- vsntprintf_l function
- _vsntprintf function
- _vsnprintf_l function
- vsnprintf function
- _vsntprintf_l function
- vsnprintf_l function
- _vsnwprintf function
- _vsnprintf function
- formatted text [C++]
- vsnwprintf function
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
caps.latest.revision: "35"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 710f4119ef943be5b58e4b617c1da1bc75e01c3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="vsnprintf-vsnprintf-vsnprintfl-vsnwprintf-vsnwprintfl"></a>vsnprintf、_vsnprintf、_vsnprintf_l、_vsnwprintf、_vsnwprintf_l
引数リストへのポインターを使用して、書式付き出力を書き込みます。 これらの関数のセキュリティを強化したバージョンを使用できます。「[vsnprintf_s、_vsnprintf_s、_vsnprintf_s_l、_vsnwprintf_s、_vsnwprintf_s_l](../../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
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
  
 詳細については、「 [printf 関数と wprintf 関数の書式指定フィールド](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」を参照してください。  
  
## <a name="return-value"></a>戻り値  
 `vsnprintf` 関数は、書き込まれた文字数を返します。終端の null 文字はその数に含まれません。 `count` で指定されたバッファー サイズが、`format` と `argptr` によって指定された出力を格納するのに十分な大きさではない場合、`vsnprintf` の戻り値は `count` が十分な大きさであった場合に書き込まれる文字数になります。終端の null 文字はその数に含まれません。 戻り値が `count` - 1 を超える場合、出力は切り捨てられています。 戻り値 -1 は、エンコード エラーが発生したことを示します。  
  
 書き込む文字数が `count` 以下である場合、`_vsnprintf` と `_vsnwprintf` の両方の関数が返すのは、書き込まれた文字数です。書き込む文字数が `count` を超える場合、これらの関数は -1 を返し、出力が切り捨てられたことを示します。  
  
 これらすべての関数によって返される値には、書き込まれているかどうかを問わず、終端の null は含まれません。 `count` がゼロの場合、返される値は、関数によって書き込まれることになる、終端の null を含まない文字数です。 この結果を用いて文字列と終端の null に対して十分なバッファー領域を割り当て、関数を再び呼び出してバッファーを埋めることができます。  
  
 `format` が `NULL`の場合、または `buffer` が NULL で `count` がゼロでない場合、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は -1 を返し、 `errno` を `EINVAL`に設定します。  
  
## <a name="remarks"></a>コメント  
 これらの各関数は、引数リストへのポインターを取り、データを書式指定して、 `count` 文字数までの文字を `buffer`が指すメモリに書き込みます。 `vsnprintf` 関数は、出力が切り捨てられる場合でも常に null 終端記号を書き込みます。 `_vsnprintf` と `_vsnwprintf`を使用するときは、終端に空きがある場合 (つまり、書き込む文字数が `count`未満の場合) に限り、バッファーは null で終わります。  
  
> [!IMPORTANT]
>  特定の種類のセキュリティ リスクを防ぐため、 `format` がユーザー定義の文字列ではないことを確認してください。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
> [!NOTE]
>  `_vsnprintf`、 `_vsnprintf_l`、 `_vsnwprintf` 、 `_vsnwprintf_l`を呼び出すときに、終端の null 用の空きを確保するために、 `count` を必ずバッファー長未満にし、この関数を呼び出す前にバッファーを null に初期化してください。  
>   
>  `vsnprintf` では終端の null を常に書き込むため、`count` パラメーターはバッファーのサイズに等しい場合があります。  
  
 Visual Studio 2015 および Windows 10 で UCRT と共に開始する場合、         `vsnprintf` は `_vsnprintf`と同一ではなくなります。 `vsnprintf` 関数は C99 規格に準拠しており、`_vnsprintf` 関数は以前の Visual Studio コードとの後方互換性のために保持されています。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vsntprintf`|`_vsnprintf`|`_vsnprintf`|`_vsnwprintf`|  
|`_vsntprintf_l`|`_vsnprintf_l`|`_vsnprintf_l`|`_vsnwprintf_l`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|  
|-------------|---------------------------|-------------------------------|  
|`vsnprintf`、 `_vsnprintf`、 `_vsnprintf_l`|\<stdio.h>|\<stdio.h> または \<cstdio>|  
|`_vsnwprintf`, `_vsnwprintf_l`|\<stdio.h> または \<wchar.h>|\<stdio.h>、\<wchar.h>、\<cstdio>、または \<cwchar>|  
  
 `_vsnprintf`、 `_vsnprintf_l`、 `_vsnwprintf` 、 `_vsnwprintf_l` の各関数は、Microsoft 固有の関数です。 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```C  
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
    va_end(args);
}  
  
int main() {  
    FormatOutput(L"%ls %ls", L"Hi", L"there");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");  
}  
```  
  
```Output  
nSize: 8, buff: Hi there  
nSize: 9, buff: Hi there!  
nSize: -1, buff: Hi there!  
```  
  
 代わりに vsnprintf を使用し、パラメータに小さな文字列を指定すると、挙動が変化します。 `count` パラメーターにはバッファー全体のサイズを指定でき、戻り値は `count` が十分大きかった場合に書き込まれていた文字数になります。  
  
## <a name="example"></a>例  
  
```C  
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
    va_end(args);  
}  
  
int main() {  
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null  
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null  
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null  
}  
```  
  
```Output  
nSize: 8, buff: Hi there  
nSize: 9, buff: Hi there!  
nSize: 10, buff: Hi there!  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf、_fprintf_l、fwprintf、_fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg、va_copy、va_end、va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
