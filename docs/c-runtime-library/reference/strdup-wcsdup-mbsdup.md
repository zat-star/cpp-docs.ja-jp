---
title: "_strdup、_wcsdup、_mbsdup | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strdup"
  - "_mbsdup"
  - "_wcsdup"
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
  - "_tcsdup"
  - "mbsdup"
  - "_mbsdup"
  - "_strdup"
  - "_ftcsdup"
  - "_wcsdup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wcsdup 関数"
  - "ftcsdup 関数"
  - "_ftcsdup 関数"
  - "mbsdup 関数"
  - "strdup 関数"
  - "_strdup 関数"
  - "_wcsdup 関数"
  - "コピー (文字列を)"
  - "複製 (文字列を)"
  - "コピー文字列 [C++]"
  - "_mbsdup 関数"
  - "複製文字列 [C++]"
  - "tcsdup 関数"
  - "_tcsdup 関数"
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _strdup、_wcsdup、_mbsdup
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列を複製します。  
  
> [!IMPORTANT]
>  `_mbsdup` は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] で実行するアプリケーションでは使用できません。 詳しくは、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## 構文  
  
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
  
#### パラメーター  
 `strSource`  
 NULL で終わる元の文字列。  
  
## 戻り値  
 これらの各関数は、コピーされた文字列の格納場所へのポインター、またはストレージを割り当てることができない場合は `NULL` を返します。  
  
## 解説  
 `_strdup` 関数は、[malloc](../../c-runtime-library/reference/malloc.md) を呼び出して `strSource` のコピーにストレージ領域を割り当て、割り当てられた領域に `strSource` をコピーします。  
  
 `_wcsdup` 関数と `_mbsdup` 関数は、`_strdup` 関数のワイド文字バージョンとマルチバイト文字バージョンです。`_wcsdup` 関数の引数と戻り値はワイド文字列で、`_mbsdup` 関数の引数と戻り値はマルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsdup`|`_strdup`|`_mbsdup`|`_wcsdup`|  
  
 `strSource` のコピーのストレージ領域を割り当てるために `_strdup` が `malloc` を呼び出すので、`_strdup` の呼び出しから返されたポインターに対して [free](../../c-runtime-library/reference/free.md) ルーチンを呼び出して、このメモリを常に解放することをお勧めします。  
  
 `_DEBUG` と `_CRTDBG_MAP_ALLOC` が定義されている場合、デバッグのメモリ割り当てを考慮して、`_strdup` と `_wcsdup` は `_strdup_dbg` と `_wcsdup_dbg` の呼び出しによって置き換えられます。 詳細については、「[\_strdup\_dbg、\_wcsdup\_dbg](../Topic/_strdup_dbg,%20_wcsdup_dbg.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_strdup`|\<string.h\>|  
|`_wcsdup`|\<string.h\> または \<wchar.h\>|  
|`_mbsdup`|\<mbstring.h\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 使用例  
  
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
Original: This is the buffer text Copy:     This is the buffer text  
```  
  
## 同等の .NET Framework 関数  
 [System::String::Clone](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat、wcscat、\_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp、wcscmp、\_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strncat、\_strncat\_l、wcsncat、\_wcsncat\_l、\_mbsncat、\_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、\_strncpy\_l、wcsncpy、\_wcsncpy\_l、\_mbsncpy、\_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、\_mbsrchr、\_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn、wcsspn、\_mbsspn、\_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)