---
title: "strspn、wcsspn、_mbsspn、_mbsspn_l | Microsoft Docs"
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
  - "_mbsspn_l"
  - "wcsspn"
  - "strspn"
  - "_mbsspn"
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
  - "_ftcsspn"
  - "wcsspn"
  - "_mbsspn"
  - "_tcsspn"
  - "strspn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsspn 関数"
  - "_mbsspn 関数"
  - "_mbsspn_l 関数"
  - "_tcsspn 関数"
  - "ftcsspn 関数"
  - "mbsspn 関数"
  - "mbsspn_l 関数"
  - "文字列 [C++], 検索"
  - "strspn 関数"
  - "部分文字列, 検索"
  - "tcsspn 関数"
  - "wcsspn 関数"
ms.assetid: d077284a-809f-4068-959e-c6d6262677eb
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strspn、wcsspn、_mbsspn、_mbsspn_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列の中で、文字セットに含まれない最初の文字へのインデックスを返します。  
  
> [!IMPORTANT]
>  `_mbsspn` および `_mbsspn_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
size_t strspn(  
   const char *str,  
   const char *strCharSet   
);  
size_t wcsspn(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
);  
size_t _mbsspn(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
);  
size_t _mbsspn_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `str`  
 NULL で終わる検索対象の文字列。  
  
 `strCharSet`  
 NULL で終わる文字セット。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `strCharSet` の文字だけで構成される `str` の部分文字列の長さを示す整数値を返します。`str` が `strCharSet` にない文字で始まる場合、関数は 0 を返します。  
  
## 解説  
 `strspn` 関数は、`str` 文字列の中で、`strCharSet` の文字セットに含まれない最初の文字へのインデックスを返します。  検索には、終端の NULL 文字は含まれません。  
  
 `wcsspn` 関数と `_mbsspn` 関数は、`strspn` 関数のワイド文字バージョンとマルチバイト文字バージョンです。`wcsspn` 関数の引数はワイド文字列で、`_mbsspn` 関数の引数はマルチバイト文字列です。  `_mbsspn` はそのパラメーターを検証します。  `str` または `strCharSet` が`NULL`の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md) "に説明されているように、呼び出されます。  実行の継続が許可された場合、`_mbspn` は `errno` を `EINVAL` に設定し、0 を返します。  `strspn` および `wcsspn` は、パラメーターを検証しません。  それ以外では、これらの関数の動作は同じです。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないこの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcsspn`|`strspn`|`_mbsspn`|`wcsspn`|  
|**適用なし**|**適用なし**|`_mbsspn_l`|**適用なし**|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strspn`|\<string.h\>|  
|`wcsspn`|\<string.h\> または \<wchar.h\>|  
|`_mbsspn`, `_mbsspn_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_strspn.c  
// This program uses strspn to determine  
// the length of the segment in the string "cabbage"  
// consisting of a's, b's, and c's. In other words,  
// it finds the first non-abc letter.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[] = "cabbage";  
   int  result;  
   result = strspn( string, "abc" );  
   printf( "The portion of '%s' containing only a, b, or c "  
           "is %d bytes long\n", string, result );  
}  
```  
  
  **a、b、または c のみが含まれる 'cabbage' の部分は 5 バイトの長さです。**   
## 同等の .NET Framework 関数  
 [System::String::Substring](https://msdn.microsoft.com/en-us/library/system.string.substring.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strspnp、\_wcsspnp、\_mbsspnp、\_mbsspnp\_l](../Topic/_strspnp,%20_wcsspnp,%20_mbsspnp,%20_mbsspnp_l.md)   
 [strcspn、wcscspn、\_mbscspn、\_mbscspn\_l](../Topic/strcspn,%20wcscspn,%20_mbscspn,%20_mbscspn_l.md)   
 [strncat、\_strncat\_l、wcsncat、\_wcsncat\_l、\_mbsncat、\_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、\_strncpy\_l、wcsncpy、\_wcsncpy\_l、\_mbsncpy、\_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、\_mbsrchr、\_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)