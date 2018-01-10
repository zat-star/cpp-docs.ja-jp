---
title: "strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbslen
- _mbslen_l
- _mbstrlen
- wcslen
- _mbstrlen_l
- strlen
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
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstrlen
- wcslen
- _tcslen
- _ftcslen
- strlen
- _mbslen
dev_langs: C++
helpviewer_keywords:
- wcslen function
- string length, getting
- ftcslen function
- lengths, strings
- mbstrlen_l function
- _mbslen_l function
- _tcslen function
- mbslen_l function
- mbslen function
- _mbstrlen function
- strings [C++], getting length
- mbstrlen function
- _mbstrlen_l function
- _ftcslen function
- tcslen function
- strlen function
- _mbslen function
ms.assetid: 16462f2a-1e0f-4eb3-be55-bf1c83f374c2
caps.latest.revision: "32"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c7277a52dfbc77bb41fe0603129813ee682b4bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="strlen-wcslen-mbslen-mbslenl-mbstrlen-mbstrlenl"></a>strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l
現在のロケールまたは指定されたロケールを使用し、文字列の長さを取得します。 これらの関数についてセキュリティ保護が強化されたバージョンを使用できます。「[strnlen、strnlen_s、wcsnlen、wcsnlen_s、_mbsnlen、_mbsnlen_l、_mbstrnlen、_mbstrnlen_l](../../c-runtime-library/reference/strnlen-strnlen-s.md)」をご覧ください  
  
> [!IMPORTANT]
>  `_mbslen`、`_mbslen_l`、`_mbstrlen`、および `_mbstrlen_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
size_t strlen(  
   const char *str  
);  
size_t wcslen(  
   const wchar_t *str   
);  
size_t _mbslen(  
   const unsigned char *str   
);  
size_t _mbslen_l(  
   const unsigned char *str,  
   _locale_t locale  
);  
size_t _mbstrlen(  
   const char *str  
);  
size_t _mbstrlen_l(  
   const char *str,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 NULL で終わる文字列。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は、`str` の文字数を返します。終端の `NULL` は含まれません。 文字列に無効なマルチバイト文字が含まれる場合に `_mbstrlen` を返す `_mbstrlen_l` と `((size_t)(-1))` を除いて、エラーを示す戻り値は予約されていません。  
  
## <a name="remarks"></a>コメント  
 `strlen` は文字列を 1 バイト文字列として扱うため、マルチバイト文字が含まれている場合でも、戻り値は常にバイト数と同じです。 `wcslen` は `strlen` のワイド文字バージョンです。`wcslen` の引数はワイド文字列で、文字数はワイド (2 バイト) 文字の単位です。 それ以外では、`wcslen` と `strlen` の動作は同じです。  
  
 **セキュリティに関するメモ** これらの関数は、バッファー オーバーランが原因で発生する潜在的な脅威の影響を受けます。 バッファー オーバーランは、システムを攻撃するときによく使用される方法であり、その結果、認められていない権限が昇格されます。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcslen`|`strlen`|`strlen`|`wcslen`|  
|`_tcsclen`|`strlen`|`_mbslen`|`wcslen`|  
|`_tcsclen_l`|`strlen`|`_mbslen_l`|`wcslen`|  
  
 `_mbslen` と `_mbslen_l` は、マルチバイト文字列のマルチバイト文字数を返しますが、マルチバイト文字の有効性はテストしません。 `_mbstrlen` と `_mbstrlen_l` は、マルチバイト文字の有効性をテストし、マルチバイト文字のシーケンスを認識します。 `_mbstrlen` または `_mbstrlen_l` に渡された文字列に、該当するコード ページにおいて無効なマルチバイト文字が含まれる場合、これらの関数は -1 を返し、`errno` を `EILSEQ` に設定します。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定に影響されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`strlen`|\<string.h>|  
|`wcslen`|\<string.h> または \<wchar.h>|  
|`_mbslen`, `_mbslen_l`|\<mbstring.h>|  
|`_mbstrlen`, `_mbstrlen_l`|\<stdlib.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strlen.c  
// Determine the length of a string. For the multi-byte character  
// example to work correctly, the Japanese language support for  
// non-Unicode programs must be enabled by the operating system.  
  
#include <string.h>  
#include <locale.h>  
  
int main()  
{  
   char* str1 = "Count.";  
   wchar_t* wstr1 = L"Count.";  
   char * mbstr1;  
   char * locale_string;  
  
   // strlen gives the length of single-byte character string  
   printf("Length of '%s' : %d\n", str1, strlen(str1) );  
  
   // wstrlen gives the length of a wide character string  
   wprintf(L"Length of '%s' : %d\n", wstr1, wcslen(wstr1) );  
  
   // A multibyte string: [A] [B] [C] [katakana A] [D] [\0]  
   // in Code Page 932. For this example to work correctly,  
   // the Japanese language support must be enabled by the  
   // operating system.  
   mbstr1 = "ABC" "\x83\x40" "D";  
  
   locale_string = setlocale(LC_CTYPE, "Japanese_Japan");  
  
   if (locale_string == NULL)  
   {  
      printf("Japanese locale not enabled. Exiting.\n");  
      exit(1);  
   }  
   else  
   {  
      printf("Locale set to %s\n", locale_string);  
   }  
  
   // _mbslen will recognize the Japanese multibyte character if the  
   // current locale used by the operating system is Japanese  
   printf("Length of '%s' : %d\n", mbstr1, _mbslen(mbstr1) );  
  
   // _mbstrlen will recognize the Japanese multibyte character  
   // since the CRT locale is set to Japanese even if the OS locale  
   // isnot.   
   printf("Length of '%s' : %d\n", mbstr1, _mbstrlen(mbstr1) );  
   printf("Bytes in '%s' : %d\n", mbstr1, strlen(mbstr1) );     
  
}  
```  
  
```Output  
Length of 'Count.' : 6  
Length of 'Count.' : 6  
Length of 'ABCァD' : 5  
Length of 'ABCァD' : 5  
Bytes in 'ABCァD' : 6  
```  
  
## <a name="see-also"></a>参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcat、wcscat、_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll 関数](../../c-runtime-library/strcoll-functions.md)   
 [strcpy、wcscpy、_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)