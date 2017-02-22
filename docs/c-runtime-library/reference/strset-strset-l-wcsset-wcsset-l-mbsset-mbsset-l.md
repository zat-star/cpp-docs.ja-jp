---
title: "_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsset"
  - "_mbsset"
  - "_strset_l"
  - "_strset"
  - "_wcsset_l"
  - "_mbsset_l"
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
  - "mbsset"
  - "_strset_l"
  - "_mbsset"
  - "_strset"
  - "mbsset_l"
  - "strset_l"
  - "_wcsset"
  - "_ftcsset"
  - "wcsset_l"
  - "_tcsset_l"
  - "_mbsset_l"
  - "_wcsset_l"
  - "_fstrset"
  - "_tcsset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstrset 関数"
  - "_ftcsset 関数"
  - "_mbsset 関数"
  - "_mbsset_l 関数"
  - "_strset 関数"
  - "_strset_l 関数"
  - "_tcsset 関数"
  - "_tcsset_l 関数"
  - "_wcsset 関数"
  - "_wcsset_l 関数"
  - "文字 [C++], 設定"
  - "fstrset 関数"
  - "ftcsset 関数"
  - "mbsset 関数"
  - "mbsset_l 関数"
  - "文字列 [C++], 設定 (文字を)"
  - "strset_l 関数"
  - "tcsset 関数"
  - "tcsset_l 関数"
  - "wcsset_l 関数"
ms.assetid: c42ded42-2ed9-4f06-a0a9-247ba305473a
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# _strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列の文字をある文字に設定します。  これらの関数のセキュリティを強化したバージョンについては、「[\_strset\_s、\_wcsset\_s、\_wcsset\_s\_l、\_mbsset\_s、\_mbsset\_s\_l](../Topic/_strset_s,%20_strset_s_l,%20_wcsset_s,%20_wcsset_s_l,%20_mbsset_s,%20_mbsset_s_l.md)」を参照してください。  
  
> [!IMPORTANT]
>  `_mbsset` と `_mbsset_l` は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
char *_strset(  
   char *str,  
   int c   
);  
char *_strset_l(  
   char *str,  
   int c,  
   locale_t locale  
);  
wchar_t *_wcsset(  
   wchar_t *str,  
   wchar_t c   
);  
wchar_t *_wcsset_l(  
   wchar_t *str,  
   wchar_t c,  
   locale_t locale  
);  
unsigned char *_mbsset(  
   unsigned char *str,  
   unsigned int c   
);  
unsigned char *_mbsset_l(  
   unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `str`  
 NULL で終わる、設定される文字列。  
  
 `c`  
 文字設定。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 変更された文字列へのポインターを返します。  
  
## 解説  
 `_strset` 関数は `str` のすべての文字 \(終端の NULL 文字を除く\) を `char` に変換された `c` に設定します。  `_wcsset` と `_mbsset_l` は `_strset` のワイド文字バージョンとマルチバイト文字バージョンであり、それに応じて引数と戻り値のデータ型が異なります。  それ以外では、これらの関数の動作は同じです。  
  
 `_mbsset` はそのパラメーターを検証します。  `str` が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`_mbsset` は `NULL` を返し、`errno` を `EINVAL` に設定します。  `_strset` および `_wcsset` は、パラメーターを検証しません。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないバージョンは現在のロケールを使用し、`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて、これらの関数のバージョンは同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
> [!IMPORTANT]
>  これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。  バッファー オーバーランは、認められていない特権の昇格の原因となるため、システムの攻撃に使用される可能性があります。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcsset`|`_strset`|`_mbsset`|`_wcsset`|  
|`_tcsset_l`|`_strset_l`|`_mbsset_l`|`_wcsset_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_strset`|\<string.h\>|  
|`_strset_l`|\<tchar.h\>|  
|`_wcsset`|\<string.h\> または \<wchar.h\>|  
|`_wcsset_l`|\<tchar.h\>|  
|`_mbsset`, `_mbsset_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_strset.c  
// compile with: /W3  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[] = "Fill the string with something.";  
   printf( "Before: %s\n", string );  
   _strset( string, '*' ); // C4996  
   // Note: _strset is deprecated; consider using _strset_s instead  
   printf( "After:  %s\n", string );  
}  
```  
  
  **前: 何かで文字列を埋めます。**  
**後:  \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbset、\_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat、wcscat、\_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp、wcscmp、\_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strcpy、wcscpy、\_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [\_strnset、\_strnset\_l、\_wcsnset、\_wcsnset\_l、\_mbsnset、\_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)