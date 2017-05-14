---
title: "strcpy、wcscpy、_mbscpy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strcpy
- wcscpy
- _mbscpy
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
- _mbscpy
- _ftcscpy
- wcscpy
- _tcscpy
- strcpy
dev_langs:
- C++
helpviewer_keywords:
- strcpy function
- tcscpy function
- ftcscpy function
- mbscpy function
- wcscpy function
- copying strings
- strings [C++], copying
- _tcscpy function
- _ftcscpy function
- _mbscpy function
ms.assetid: f97a4f81-e9ee-4f15-888a-0fa5d7094c5a
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 940983d8bb5795d44a78f9049c351941db41afb7
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="strcpy-wcscpy-mbscpy"></a>strcpy、wcscpy、_mbscpy
文字列をコピーします。 これらの関数にはセキュリティが強化されたバージョンがあります。「[strcpy_s、wcscpy_s、_mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)」をご覧ください。  
  
> [!IMPORTANT]
>  `_mbscpy` は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] で実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *strcpy(  
   char *strDestination,  
   const char *strSource   
);  
wchar_t *wcscpy(  
   wchar_t *strDestination,  
   const wchar_t *strSource   
);  
unsigned char *_mbscpy(  
   unsigned char *strDestination,  
   const unsigned char *strSource   
);  
template <size_t size>  
char *strcpy(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
wchar_t *wcscpy(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
unsigned char *_mbscpy(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `strDestination`  
 対象文字列。  
  
 `strSource`  
 NULL で終わる元の文字列。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は、コピー先文字列を返します。 エラーを示す戻り値は予約されていません。  
  
## <a name="remarks"></a>コメント  
 `strcpy` 関数は、`strSource` を、終端の NULL 文字も含めて、`strDestination` で指定された場所にコピーします。 コピー元とコピー先の文字列が重なり合っている場合の `strcpy` 関数の動作は未定義です。  
  
> [!IMPORTANT]
>  `strcpy` が、`strDestination` をコピーする前に、`strSource` に十分な領域があるかどうかを確認しないことが、バッファー オーバーランの潜在的な原因です。 したがって、代わりに [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) の使用をお勧めします。  
  
 `wcscpy` 関数と `_mbscpy` 関数は、それぞれ、`strcpy` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `wcscpy` 関数の引数と戻り値はワイド文字列で、`_mbscpy` 関数の引数と戻り値はマルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscpy`|`strcpy`|`_mbscpy`|`wcscpy`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strcpy`|\<string.h>|  
|`wcscpy`|\<string.h> または \<wchar.h>|  
|`_mbscpy`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strcpy.c  
// compile with: /W3  
// This program uses strcpy  
// and strcat to build a phrase.  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[80];  
  
   // If you change the previous line to  
   //   char string[20];  
   // strcpy and strcat will happily overrun the string  
   // buffer.  See the examples for strncpy and strncat  
   // for safer string handling.  
  
   strcpy( string, "Hello world from " ); // C4996  
   // Note: strcpy is deprecated; use strcpy_s instead  
   strcat( string, "strcpy " );           // C4996  
   // Note: strcat is deprecated; use strcat_s instead  
   strcat( string, "and " );              // C4996  
   strcat( string, "strcat!" );           // C4996  
   printf( "String = %s\n", string );  
}  
```  
  
```Output  
String = Hello world from strcpy and strcat!  
```  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat、wcscat、_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
