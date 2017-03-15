---
title: "strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbspbrk"
  - "wcspbrk"
  - "_mbspbrk_l"
  - "strpbrk"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_fstrpbrk"
  - "_mbspbrk"
  - "strpbrk"
  - "_tcspbrk"
  - "_ftcspbrk"
  - "wcspbrk"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstrpbrk 関数"
  - "_ftcspbrk 関数"
  - "_mbspbrk 関数"
  - "_mbspbrk_l 関数"
  - "_tcspbrk 関数"
  - "文字セット [C++], スキャン (文字列を)"
  - "文字 [C++], スキャン (文字列を)"
  - "fstrpbrk 関数"
  - "ftcspbrk 関数"
  - "mbspbrk 関数"
  - "mbspbrk_l 関数"
  - "文字列 [C++], スキャン"
  - "strpbrk 関数"
  - "tcspbrk 関数"
  - "wcspbrk 関数"
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列をスキャンして、指定された文字セットの文字を検索します。  
  
> [!IMPORTANT]
>  `_mbspbrk` および `_mbspbrk_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C only  
char *strpbrk(  
   char *str,  
   const char *strCharSet   
); // C++ only  
const char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C++ only  
wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C only  
wchar_t *wcspbrk(  
   wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
const wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C only  
unsigned char *_mbspbrk(  
   unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
const unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C only  
unsigned char *_mbspbrk_l(  
   unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char* strCharSet,  
   _locale_t locale  
); // C++ only  
```  
  
#### パラメーター  
 `str`  
 NULL で終わる検索対象の文字列。  
  
 `strCharSet`  
 NULL で終わる文字セット。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `str` の `strCharSet` から最初に出現する文字へのポインター、または 2 つの文字列引数に共通の文字がない場合は `NULL` ポインターを返します。  
  
## 解説  
 `strpbrk` 関数は、`strCharSet` の文字セットに属する `str` で最初に出現する文字へのポインターを返します。  検索には、終端の NULL 文字は含まれません。  
  
 `wcspbrk` 関数と `_mbspbrk` 関数は、`strpbrk` 関数のワイド文字バージョンとマルチバイト文字バージョンです。  `wcspbrk` 関数の引数と戻り値はワイド文字列で、`_mbspbrk` 関数の引数と戻り値はマルチバイト文字列です。  
  
 `_mbspbrk` はそのパラメーターを検証します。  `str` または `strCharSet` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`_mbspbrk` は `NULL` を返し、`errno` を `EINVAL` に設定します。  `strpbrk` および `wcspbrk` は、パラメーターを検証しません。  それ以外では、これらの関数の動作は同じです。  
  
 `_mbspbrk` は、`_mbspbrk` が [size\_t](../../c-runtime-library/standard-types.md) 型の値ではなくポインターを返す場合を除いて、`_mbscspn` と同様です。  
  
 C では、これらの関数は、最初の引数に `const` ポインターを受け取ります。  C\+\+ では、2 つのオーバーロードを使用できます。  `const` へのポインターを受け取るオーバーロードでは、`const` へのポインターが返されます。非 `const` へのポインターを受け取るバージョンでは、非 `const` へのポインターが返されます。  この関数の `const` と非 `const` の両方のバージョンが使用できる場合、\_CONST\_CORRECT\_OVERLOADS というマクロが定義されます。  C\+\+ のいずれのオーバーロードでも、非 `const` の動作が求められる場合は、シンボル \_CONST\_RETURN を定義してください。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|  
|**適用なし**|**適用なし**|`_mbspbrk_l`|**適用なし**|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strpbrk`|\<string.h\>|  
|`wcspbrk`|\<string.h\> または \<wchar.h\>|  
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_strpbrk.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";  
   char *result = NULL;  
  
   // Return pointer to first digit in "string".  
   printf( "1: %s\n", string );  
   result = strpbrk( string, "0123456789" );  
   printf( "2: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "3: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "4: %s\n", result );  
}  
```  
  
  **1: The 3 men and 2 boys ate 5 pigs**  
**2: 3 men and 2 boys ate 5 pigs**  
**3: 2 boys ate 5 pigs**  
**4: 5 pigs**   
## 同等の .NET Framework 関数  
 [System::String::IndexOfAny](https://msdn.microsoft.com/en-us/library/system.string.indexofany.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn、wcscspn、\_mbscspn、\_mbscspn\_l](../Topic/strcspn,%20wcscspn,%20_mbscspn,%20_mbscspn_l.md)   
 [strchr、wcschr、\_mbschr、\_mbschr\_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strrchr、wcsrchr、\_mbsrchr、\_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)