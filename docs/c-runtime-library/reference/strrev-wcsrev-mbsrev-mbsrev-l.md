---
title: "_strrev、_wcsrev、_mbsrev、_mbsrev_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsrev"
  - "_mbsrev"
  - "_strrev"
  - "_mbsrev_l"
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
  - "_strrev"
  - "_ftcsrev"
  - "_tcsrev"
  - "mbsrev"
  - "mbsrev_l"
  - "_wcsrev_fstrrev"
  - "_mbsrev"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsrev 関数"
  - "_mbsrev 関数"
  - "_mbsrev_l 関数"
  - "_strrev 関数"
  - "_tcsrev 関数"
  - "_wcsrev 関数"
  - "文字 [C++], 反転 (順序を)"
  - "文字 [C++], 切り替え"
  - "ftcsrev 関数"
  - "mbsrev 関数"
  - "mbsrev_l 関数"
  - "反転 (文字列を)"
  - "文字列 [C++], 反転"
  - "strrev 関数"
  - "tcsrev 関数"
  - "wcsrev 関数"
ms.assetid: 87863e89-4fa0-421c-af48-25d8516fe72f
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _strrev、_wcsrev、_mbsrev、_mbsrev_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列の文字を反転させます。  
  
> [!IMPORTANT]
>  `_mbsrev` と `_mbsrev_l` は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
char *_strrev(  
   char *str   
);  
wchar_t *_wcsrev(  
   wchar_t *str   
);  
unsigned char *_mbsrev(  
   unsigned char *str   
);  
unsigned char *_mbsrev_l(  
   unsigned char *str,  
   _locale_t locale   
);  
```  
  
#### パラメーター  
 `str`  
 NULL で終わる反転対象の文字列。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 変更された文字列へのポインターを返します。  エラーを示す戻り値は予約されていません。  
  
## 解説  
 `_strrev` 関数は、`string` の文字の順序を反転させます。  終端の NULL 文字はそのまま保持されます。  `_wcsrev` 関数と `_mbsrev` 関数は、`_strrev` 関数のワイド文字バージョンとマルチバイト文字バージョンです。  `_wcsrev` 関数の引数と戻り値はワイド文字列で、`_mbsrev` 関数の引数と戻り値はマルチバイト文字列です。  `_mbsrev` については、`string` の各マルチバイト文字のバイトの順序は変更されません。  それ以外では、これらの関数の動作は同じです。  
  
 `_mbsrev` はそのパラメーターを検証します。  `string1` または `string2` が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`_mbsrev` は `NULL` を返し、`errno` を `EINVAL` に設定します。  `_strrev` および `_wcsrev` は、パラメーターを検証しません。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないバージョンが現在のロケールを使用し、`_l` サフィックスが付いているバージョンが渡されたロケール パラメーターを代わりに使用する点を除いて、これらの関数のバージョンは同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
> [!IMPORTANT]
>  これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。  バッファー オーバーランは、認められていない特権の昇格の原因となるため、システムの攻撃に使用される可能性があります。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcsrev`|`_strrev`|`_mbsrev`|`_wcsrev`|  
|**適用なし**|**適用なし**|`_mbsrev_l`|**適用なし**|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_strrev`|\<string.h\>|  
|`_wcsrev`|\<string.h\> または \<wchar.h\>|  
|`_mbsrev`, `_mbsrev_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_strrev.c  
// This program checks a string to see  
// whether it is a palindrome: that is, whether  
// it reads the same forward and backward.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* string = "Able was I ere I saw Elba";  
   int result;  
  
   // Reverse string and compare (ignore case):  
   result = _stricmp( string, _strrev( _strdup( string ) ) );  
   if( result == 0 )  
      printf( "The string \"%s\" is a palindrome\n", string );  
   else  
      printf( "The string \"%s\" is not a palindrome\n", string );  
}  
```  
  
  **文字列 "Able was I ere I saw Elba" は回文です。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcpy、wcscpy、\_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [\_strset、\_strset\_l、\_wcsset、\_wcsset\_l、\_mbsset、\_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)