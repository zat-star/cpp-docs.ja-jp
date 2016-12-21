---
title: "_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l | Microsoft Docs"
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
  - "_stricmp_l"
  - "_mbsicmp"
  - "_wcsicmp"
  - "_mbsicmp_l"
  - "_stricmp"
  - "_wcsicmp_l"
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
  - "_ftcsicmp"
  - "_stricmp"
  - "wcsicmp_l"
  - "_wcsicmp"
  - "_tcsicmp"
  - "_strcmpi"
  - "stricmp_l"
  - "_mbsicmp"
  - "_fstricmp"
  - "mbsicmp_l"
  - "mbsicmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fstricmp 関数"
  - "_ftcsicmp 関数"
  - "_mbsicmp 関数"
  - "_mbsicmp_l 関数"
  - "_strcmpi 関数"
  - "_stricmp 関数"
  - "_stricmp_l 関数"
  - "_tcsicmp 関数"
  - "_wcsicmp 関数"
  - "_wcsicmp_l 関数"
  - "fstricmp 関数"
  - "ftcsicmp 関数"
  - "mbsicmp 関数"
  - "mbsicmp_l 関数"
  - "stricmp_l 関数"
  - "文字列比較 [C++], 小文字"
  - "文字列 [C++], 比較"
  - "tcsicmp 関数"
  - "wcsicmp_l 関数"
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
caps.latest.revision: 28
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列の大文字と小文字を区別しない比較を実行します。  
  
> [!IMPORTANT]
>  `_mbsicmp` および `_mbsicmp_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _stricmp(  
   const char *string1,  
   const char *string2   
);  
int _wcsicmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricmp_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `string1, string2`  
 Null で終わる比較対象の文字列。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 戻り値は、次のように `string1` と `string2` の関係を示します。  
  
|戻り値|説明|  
|---------|--------|  
|\< 0|`string1` が `string2` より小さい|  
|0|`string1` が `string2` と同じ|  
|\> 0|`string1` が `string2` より大きい|  
  
 エラーが発生した場合、`_mbsicmp` は `_NLSCMPERROR` を返します。これは、\<string.h\> および \<mbstring.h\> で定義されています。  
  
## 解説  
 `_stricmp` 関数は、各文字を小文字に変換した後、`string1` と `string2` で序数に基づく比較を行い、その関係を示す値を返します。  `_stricmp` と `_stricoll` の相違点は、`_stricmp` による比較では、どの文字が大文字または小文字であるかを決定する `LC_CTYPE` の影響のみを受けるという点です。  `_stricoll` 関数は、ロケールの `LC_CTYPE` と `LC_COLLATE` の両方のカテゴリに従って文字列を比較しますが、これには大文字と小文字、および照合順序の両方が含まれます。  `LC_COLLATE` カテゴリの詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」および「[ロケールのカテゴリ](../../c-runtime-library/locale-categories.md)」を参照してください。  `_l` サフィックスが付いていないこれらの関数のバージョンでは、ロケールに依存する動作に現在のロケールを使用します。  サフィックスが付いているバージョンは、代わりに渡されたロケールを使用する点を除き、同じです。  ロケールが設定されていない場合は、C ロケールが使用されます。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください  
  
> [!NOTE]
>  `_stricmp` は `_strcmpi` と同じです。  この 2 つは区別なく使用できますが、推奨する標準は `_stricmp` です。  
  
 `_strcmpi`関数は `_stricmp`と同じですが、下位互換性を維持するために用意されています。  
  
 `_stricmp` は小文字の比較を実行するので、予期しない動作が発生する場合があります。  
  
 `_stricmp` による大文字と小文字の変換が比較の結果に与える影響について、JOHNSTON と JOHN\_HENRY という 2 つの文字列を使用して説明します。  "\_" の ASCII 値は、小文字の S よりも小さいので、文字列 JOHN\_HENRY は JOHNSTON よりも小さいと見なされます。  実際に、91 ～ 96 の ASCII 値を持つ文字は、他の文字よりも小さいと見なされます。  
  
 [strcmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md) 関数の代わりに `_stricmp` 関数を使用すると、JOHN\_HENRY は JOHNSTON よりも大きいと判断されます。  
  
 `_wcsicmp` 関数と `_mbsicmp` 関数は、`_stricmp` 関数のワイド文字バージョンとマルチバイト文字バージョンです。  `_wcsicmp` 関数の引数と戻り値はワイド文字列で、`_mbsicmp` 関数の引数と戻り値はマルチバイト文字列です。  `_mbsicmp` は現在のマルチバイト コード ページに基づいてマルチバイト文字のシーケンスを認識し、エラーが発生した場合は `_NLSCMPERROR` を返します  詳細については、「[コード ページ](../../c-runtime-library/code-pages.md)」を参照してください。  それ以外では、これらの関数の動作は同じです。  
  
 `_wcsicmp` と `wcscmp` の動作は、`wcscmp` がその引数を比較する前に小文字に変換しないという点以外は同じです。  `_mbsicmp` と `_mbscmp` の動作は、`_mbscmp` がその引数を比較する前に小文字に変換しないという点以外は同じです。  
  
 [setlocale](../Topic/setlocale,%20_wsetlocale.md) で Latin 1 文字を操作するには、`_wcsicmp` を呼び出す必要があります。  既定では、C ロケールが有効になっているので、たとえば、ä は Ä と等しいと見なされません。  `setlocale` を呼び出す前に、C ロケール以外のロケールを指定して `_wcsicmp` を呼び出します。  次の例では、ロケールが `_wcsicmp`に与える影響を示します。  
  
```  
// crt_stricmp_locale.c  
#include <string.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main() {  
   setlocale(LC_ALL,"C");   // in effect by default  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails  
   setlocale(LC_ALL,"");  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds  
}  
```  
  
 また、[\_create\_locale、\_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md) を呼び出して、返されたロケール オブジェクトをパラメーターとして `_wcsicmp_l` に渡す方法もあります。  
  
 これらのすべての関数では、パラメーターの検証が行われます。  `string1` または `string2` が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsicmp`|`_stricmp`|`_mbsicmp`|`_wcsicmp`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_stricmp`, `_stricmp_l`|\<string.h\>|  
|`_wcsicmp`, `_wcsicmp_l`|\<string.h\> または \<wchar.h\>|  
|`_mbsicmp`, `_mbsicmp_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_stricmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
  **文字列の比較:**  
 **The quick brown dog jumps over the lazy fox**  
 **The QUICK brown dog jumps over the lazy fox**  
 **strcmp:   文字列 1 は文字列 2 より大きい**  
 **\_stricmp:  文字列 1 は文字列 2 と等しい**   
## 同等の .NET Framework 関数  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp、wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [\_memicmp、\_memicmp\_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcmp、wcscmp、\_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、\_mbsrchr、\_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset、\_strset\_l、\_wcsset、\_wcsset\_l、\_mbsset、\_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn、wcsspn、\_mbsspn、\_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)