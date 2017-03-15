---
title: "strncmp、wcsncmp、_mbsncmp、_mbsncmp_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strncmp"
  - "_mbsncmp"
  - "wcsncmp"
  - "_mbsncmp_l"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ftcsnccmp"
  - "_ftcsncmp"
  - "_tcsncmp"
  - "_tcsnccmp"
  - "strncmp"
  - "_mbsncmp"
  - "wcsncmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsnccmp 関数"
  - "_ftcsncmp 関数"
  - "_mbsncmp 関数"
  - "_mbsncmp_l 関数"
  - "_tcsnccmp 関数"
  - "_tcsncmp 関数"
  - "文字 [C++], 比較"
  - "ftcsnccmp 関数"
  - "ftcsncmp 関数"
  - "mbsncmp 関数"
  - "mbsncmp_l 関数"
  - "文字列比較 [C++], strncmp 関数"
  - "文字列 [C++], 比較 (文字を)"
  - "strncmp 関数"
  - "tcsnccmp 関数"
  - "tcsncmp 関数"
  - "wcsncmp 関数"
ms.assetid: 2fdbf4e6-77da-4b59-9086-488f6066b8af
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# strncmp、wcsncmp、_mbsncmp、_mbsncmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2 つの文字列を、指定した文字数まで比較します。  
  
> [!IMPORTANT]
>  `_mbsncmp` および `_mbsncmp_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int strncmp(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int wcsncmp(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsncmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,   
   _locale_t locale  
);int _mbsnbcmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### パラメーター  
 `string1, string2`  
 比較する文字列。  
  
 `count`  
 比較する文字数  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 戻り値は `string1` と `string2` の部分文字列の関係を次のように示します。  
  
|戻り値|説明|  
|---------|--------|  
|\< 0|`string1` 部分文字列は `string2` 部分文字列よりも小さい|  
|0|`string1` 部分文字列は `string2` 部分文字列と同じ|  
|\> 0|`string1` 部分文字列は `string2` 部分文字列よりも大きい|  
  
 パラメーター検証エラーが発生した場合、`_mbsncmp` および `_mbsncmp_l` は `_NLSCMPERROR` を返します。これは、\<string.h\> および \<mbstring.h\> で定義されています。  
  
## 解説  
 `strncmp` 関数は、`count` と `string1` の先頭の最大 `string2` 文字で序数に基づく比較を行い、部分文字列の間の関係を示す値を返します。  `strncmp` は `_strnicmp` の大文字と小文字を区別するバージョンです。  `wcsncmp` および `_mbsncmp` は、`_wcsnicmp` および `_mbsnicmp` の大文字と小文字を区別するバージョンです。  
  
 `wcsncmp` 関数と `_mbsncmp` 関数は、`strncmp` 関数のワイド文字バージョンとマルチバイト文字バージョンです。  `wcsncmp` 関数の引数はワイド文字列で、`_mbsncmp` 関数の引数はマルチバイト文字列です。  `_mbsncmp` はマルチバイト コード ページに基づいてマルチバイト文字のシーケンスを認識し、エラーが発生した場合は `_NLSCMPERROR` を返します。  
  
 また、`_mbsncmp` および `_mbsncmp_l` はパラメーターを検証します。  `string1` または `string2` が null ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`_mbsncmp` および `_mbsncmp_l` は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  `strncmp` および `wcsncmp` は、パラメーターを検証しません。  それ以外では、これらの関数の動作は同じです。  
  
 `_mbsncmp` および `_mbsncmp_l` の比較の動作は、ロケールの `LC_CTYPE` カテゴリの設定により影響されます。  これは、マルチバイト文字の先頭および末尾のバイトの検出を制御します。  詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_mbsncmp` は、ロケールに依存するこの動作に現在のロケールを使用します。  `_mbsncmp_l` 関数は、代わりに `locale` パラメーターを使用することを除けば、同一です。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください  ロケールが 1 バイトのロケールの場合、これらの関数の動作は `strncmp` と同一です。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsnccmp`|`strncmp`|`_mbsncmp`|`wcsncmp`|  
|`_tcsncmp`|`strncmp`|`_mbsnbcmp`|`wcsncmp`|  
|`_tccmp`|マクロまたはインライン関数にマップされます|`_mbsncmp`|マクロまたはインライン関数にマップされます|  
|**該当なし**|**該当なし**|`_mbsncmp_l`|**該当なし**|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strncmp`|\<string.h\>|  
|`wcsncmp`|\<string.h\> または \<wchar.h\>|  
|`_mbsncmp`, `_mbsncmp_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_strncmp.c  
#include <string.h>  
#include <stdio.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown fox jumps over the lazy dog";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
   printf( "Compare strings:\n      %s\n      %s\n\n",  
           string1, string2 );  
   printf( "Function:   strncmp (first 10 characters only)\n" );  
   result = strncmp( string1, string2 , 10 );  
   if( result > 0 )  
      strcpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      strcpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:      String 1 is %s string 2\n\n", tmp );  
   printf( "Function:   strnicmp _strnicmp (first 10 characters only)\n" );  
   result = _strnicmp( string1, string2, 10 );  
   if( result > 0 )  
      strcpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      strcpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:      String 1 is %s string 2\n", tmp );  
}  
```  
  
  **文字列の比較:**  
 **The quick brown dog jumps over the lazy fox**  
 **The QUICK brown fox jumps over the lazy dog**  
**関数:   strncmp \(first 10 characters only\)**  
**結果:      文字列 1 は文字列 2 より大きい**  
**関数:   strnicmp \_strnicmp \(first 10 characters only\)**  
**結果:      文字列 1 は文字列 2 と等しい**   
## 同等の .NET Framework 関数  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcmp、\_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_mbsnbicmp、\_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strcmp、wcscmp、\_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、\_mbsrchr、\_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset、\_strset\_l、\_wcsset、\_wcsset\_l、\_mbsset、\_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn、wcsspn、\_mbsspn、\_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)