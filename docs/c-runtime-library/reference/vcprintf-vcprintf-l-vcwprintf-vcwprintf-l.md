---
title: "_vcprintf、_vcprintf_l、_vcwprintf、_vcwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vcwprintf"
  - "_vcprintf_l"
  - "_vcwprintf_l"
  - "_vcprintf"
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
  - "_vcwprintf_l"
  - "_vtcprintf"
  - "vcwprintf"
  - "_vcwprintf"
  - "vcprintf_l"
  - "_vcprintf_l"
  - "_vcprintf"
  - "vcprintf"
  - "vcwprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vcprintf 関数"
  - "_vcprintf_l 関数"
  - "_vcwprintf 関数"
  - "_vcwprintf_l 関数"
  - "_vtcprintf 関数"
  - "_vtcprintf_l 関数"
  - "書式設定テキスト [C++]"
  - "vcprintf 関数"
  - "vcprintf_l 関数"
  - "vcwprintf 関数"
  - "vcwprintf_l 関数"
  - "vtcprintf 関数"
  - "vtcprintf_l 関数"
ms.assetid: 4ef8d237-6200-4b66-8731-8c57e5624bb1
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# _vcprintf、_vcprintf_l、_vcwprintf、_vcwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数リストへのポインターを使用して、書式付き出力をコンソールに書き込みます。  これらの関数のセキュリティを強化したバージョンについては、「[\_vcprintf\_s、\_vcprintf\_s\_l、\_vcwprintf\_s、\_vcwprintf\_s\_l](../../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)」を参照してください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _vcprintf(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf_l(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_l(  
   const wchar_t* format,  
   locale_t locale,  
   va_list argptr  
);  
```  
  
#### パラメーター  
 `format`  
 書式の指定。  
  
 `argptr`  
 引数リストへのポインター。  
  
 `locale`  
 使用するロケール。  
  
 詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)」を参照してください。  
  
## 戻り値  
 書き込まれた文字数。出力エラーが発生した場合は負の値を返します。  `format` が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から \-1 が返されます。  
  
## 解説  
 これらの各関数は、引数リストへのポインターを使用して、指定されたデータを書式化してコンソールに書き込みます。  `_vcwprintf` 関数は、`_vcprintf` 関数のワイド文字バージョンです。  引数としてワイド文字列を使用します。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_vtcprintf`|`_vcprintf`|`_vcprintf`|`_vcwprintf`|  
|`_vtcprintf_l`|`_vcprintf_l`|`_vcprintf_l`|`_vcwprintf_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|----------|------------|---------------|  
|`_vcprintf`, `_vcprintf_l`|\<conio.h\> および \<stdarg.h\>|\<varargs.h\>\*|  
|`_vcwprintf`, `_vcwprintf_l`|\<conio.h\> または \<wchar.h\>、および \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* UNIX V との互換性用  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_vcprintf.cpp  
// compile with: /c  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function used to print to the console.  
int eprintf(const char* format, ...)  
{  
  va_list args;  
  va_start(args, format);  
  return _vcprintf(format, args);  
}  
  
int main()  
{  
   eprintf("  (%d:%d): Error %s%d : %s\n", 10, 23, "C", 2111,  
           "<some error text>");  
   eprintf("  (Related to symbol '%s' defined on line %d).\n",  
           "<symbol>", 5 );  
}  
```  
  
  **\(10,23\): エラー C2111 : \<何らかのエラー テキスト\>**  
 **\(5 行目で定義されたシンボル '\<シンボル\>' に関連\)。**   
## 同等の .NET Framework 関数  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [\_cprintf、\_cprintf\_l、\_cwprintf、\_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg、va\_copy、va\_end、va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)