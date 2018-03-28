---
title: strcmp、wcscmp、_mbscmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- wcscmp
- _mbscmp
- strcmp
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _mbscmp
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
dev_langs:
- C++
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
caps.latest.revision: ''
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: addc2c215d0c914e3caee3dba4d32f94ca91e62c
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="strcmp-wcscmp-mbscmp"></a>strcmp、wcscmp、_mbscmp
文字列を比較します。  
  
> [!IMPORTANT]
>  `_mbscmp` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
int strcmp(  
   const char *string1,  
   const char *string2   
);  
int wcscmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `string1`, `string2`  
 Null で終わる比較対象の文字列。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数の戻り値は、`string1` から `string2` に対する、序数に基づく関係を示します。  
  
|値|string1 と string2 との関係|  
|-----------|----------------------------------------|  
|< 0|`string1` は `string2` より小さい|  
|0|`string1` は `string2` と同じ|  
|> 0|`string1` は `string2` より大きい|  
  
 パラメーター検証エラーが発生した場合、`_mbscmp` は `_NLSCMPERROR` を返します。これは、\<string.h> および \<mbstring.h> で定義されています。  
  
## <a name="remarks"></a>コメント  
 `strcmp` 関数は、`string1` と `string2` で序数に基づく比較を実行して、その関係を示す値を返します。 `wcscmp` 関数と `_mbscmp` 関数は、それぞれ、`strcmp` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `_mbscmp` は現在のマルチバイト コード ページに基づいてマルチバイト文字のシーケンスを認識し、エラーが発生した場合は `_NLSCMPERROR` を返します 詳細については、「[コード ページ](../../c-runtime-library/code-pages.md)」をご覧ください。 また、`string1` または `string2` が Null ポインターの場合、`_mbscmp` は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、`_mbscmp` は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。 `strcmp` および `wcscmp` は、パラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscmp`|`strcmp`|`_mbscmp`|`wcscmp`|  
  
 
          `strcmp` 関数と `strcoll` 関数の相違点は、`strcmp` が序数に基づく比較を行い、ロケールに影響されない点です。 `strcoll` は現在のロケールの `LC_COLLATE` カテゴリを使用して、文字列を辞書順で比較します。 `LC_COLLATE` カテゴリの詳細については、「[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。  
  
 "C"ロケールでは、文字セット (ASCII 文字セット) 内の文字の順序は、辞書式文字順序と同じです。 ただし、その他のロケールでは、文字セット内の文字の順序が辞書式順序と異なる場合があります。 たとえば、ヨーロッパの一部のロケールでは、文字 'a' (値 0x61) は文字セットで文字 'ä' (値 0xE4) の前にありますが、辞書式の順序では文字 'ä' が文字 'a' の前にあります。  
  
 文字セットと辞書式文字順序が異なるロケールでは、文字列の辞書式比較をするために `strcoll` の代わりに `strcmp` を使用できます。 あるいは、元の文字列に対して `strxfrm` を使用して、結果の文字列に対して `strcmp` を使用できます。  
  
 `strcmp` 関数では、大文字と小文字が区別されます。 `_stricmp`、`_wcsicmp`、および `_mbsicmp` は、文字列を最初に小文字の形式に変換してから比較します。 ASCII の表の 'Z' と 'a' の間にある文字 ('['、'`\`'、']'、'`^`'、'`_`'、および '```') を含む 2 つの文字列は、大文字と小文字によって異なる方法で比較されます。 たとえば、`"ABCDE"` と `"ABCD^"` の 2 つの文字列を比較する場合、小文字で比較する場合 (`"abcde"` > `"abcd^"`) と、大文字で比較する場合 (`"ABCDE"` < `"ABCD^"`) で方法が異なります。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strcmp`|<string.h>|  
|`wcscmp`|<string.h> または <wchar.h>|  
|`_mbscmp`|\<mbstring.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_strcmp.c  
  
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
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof (tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
```Output  
Compare strings:  
   The quick brown dog jumps over the lazy fox  
   The QUICK brown dog jumps over the lazy fox  
  
   strcmp:   String 1 is greater than string 2  
   _stricmp:  String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp、wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [_memicmp、_memicmp_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcoll 関数](../../c-runtime-library/strcoll-functions.md)   
 [_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)