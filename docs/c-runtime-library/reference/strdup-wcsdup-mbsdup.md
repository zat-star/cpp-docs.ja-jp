---
title: "_strdup、_wcsdup、_mbsdup | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdup
- _mbsdup
- _wcsdup
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
- _tcsdup
- mbsdup
- _mbsdup
- _strdup
- _ftcsdup
- _wcsdup
dev_langs:
- C++
helpviewer_keywords:
- wcsdup function
- ftcsdup function
- _ftcsdup function
- mbsdup function
- strdup function
- _strdup function
- _wcsdup function
- copying strings
- duplicating strings
- strings [C++], copying
- _mbsdup function
- strings [C++], duplicating
- tcsdup function
- _tcsdup function
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 959fe23b5d1af1c783bc06485cdcbcfc877b8990
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="strdup-wcsdup-mbsdup"></a>_strdup、_wcsdup、_mbsdup
文字列を複製します。  
  
> [!IMPORTANT]
>  `_mbsdup` は、                  [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。 詳細については、「                  [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
char *_strdup(  
   const char *strSource   
);  
wchar_t *_wcsdup(  
   const wchar_t *strSource   
);  
unsigned char *_mbsdup(  
   const unsigned char *strSource   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `strSource`  
 NULL で終わる元の文字列。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、コピーされた文字列の格納場所へのポインター、またはストレージを割り当てることができない場合は `NULL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_strdup` 関数は、[malloc](../../c-runtime-library/reference/malloc.md) を呼び出して`strSource` のコピーにストレージ領域を割り当て、割り当てられた領域に `strSource` をコピーします。  
  
 `_wcsdup` 関数と `_mbsdup` 関数は、 `_strdup`関数のワイド文字バージョンとマルチバイト文字バージョンです。 `_wcsdup` 関数の引数と戻り値はワイド文字列で、 `_mbsdup` 関数の引数と戻り値はマルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsdup`|`_strdup`|`_mbsdup`|`_wcsdup`|  
  
 `_strdup` のコピーのストレージ領域を割り当てるために `malloc` が `strSource`を呼び出すので、 [の呼び出しから返されたポインターに対して](../../c-runtime-library/reference/free.md) free `_strdup`ルーチンを呼び出して、このメモリを常に解放することをお勧めします。  
  
 `_DEBUG` と `_CRTDBG_MAP_ALLOC` が定義されている場合、デバッグのメモリ割り当てを考慮して、 `_strdup` と `_wcsdup` は `_strdup_dbg` と `_wcsdup_dbg` の呼び出しによって置き換えられます。 詳細については、「[_strdup_dbg、_wcsdup_dbg](../../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_strdup`|\<string.h>|  
|`_wcsdup`|\<string.h> または \<wchar.h>|  
|`_mbsdup`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strdup.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[] = "This is the buffer text";  
   char *newstring;  
   printf( "Original: %s\n", buffer );  
   newstring = _strdup( buffer );  
   printf( "Copy:     %s\n", newstring );  
   free( newstring );  
}  
```  
  
```Output  
Original: This is the buffer text  
Copy:     This is the buffer text  
```  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat、wcscat、_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
