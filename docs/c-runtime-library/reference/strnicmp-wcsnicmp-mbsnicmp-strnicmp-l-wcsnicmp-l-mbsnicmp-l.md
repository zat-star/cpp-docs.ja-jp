---
title: "_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsnicmp"
  - "_strnicmp_l"
  - "_wcsnicmp_l"
  - "_strnicmp"
  - "_mbsnicmp"
  - "_mbsnicmp_l"
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
  - "wcsnicmp_l"
  - "_strnicmp"
  - "_ftcsnicmp"
  - "mbsnicmp_l"
  - "_ftcsncicmp"
  - "mbsnicmp"
  - "_tcsncicmp"
  - "_mbsnicmp"
  - "_tcsnicmp"
  - "strnicmp_l"
  - "_wcsnicmp"
  - "_wcsnicmp_l"
  - "CORECRT_WSTRING/_wcsnicmp"
  - "CORECRT_WSTRING/_wcsnicmp_l"
  - "string/_strnicmp"
  - "string/_strnicmp_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsncicmp 関数"
  - "_ftcsnicmp 関数"
  - "_mbsnicmp 関数"
  - "_mbsnicmp_l 関数"
  - "_strnicmp 関数"
  - "_strnicmp_l 関数"
  - "_tcsncicmp 関数"
  - "_tcsnicmp 関数"
  - "_wcsnicmp 関数"
  - "_wcsnicmp_l 関数"
  - "文字 [C++], 比較"
  - "ftcsncicmp 関数"
  - "ftcsnicmp 関数"
  - "mbsnicmp 関数"
  - "mbsnicmp_l 関数"
  - "文字列比較 [C++], 小文字"
  - "文字列比較 [C++], strncmp 関数"
  - "文字列 [C++], 比較 (文字を)"
  - "strncmp 関数"
  - "strnicmp_l 関数"
  - "tcsncicmp 関数"
  - "tcsnicmp 関数"
  - "wcsnicmp 関数"
  - "wcsnicmp_l 関数"
ms.assetid: df6e5037-4039-4c85-a0a6-21d4ef513966
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

大文字小文字に関係なく、2 つの文字列の指定された数の文字を比較します。  
  
> [!IMPORTANT]
>  `_mbsnicmp` と `_mbsnicmp_l` は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _strnicmp(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsnicmp(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsnicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strnicmp_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsnicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnicmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `string1, string2`  
 Null で終わる比較対象の文字列。  
  
 `count`  
 比較する文字数  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 次のように、部分文字列間の関係を示します。  
  
|戻り値|説明|  
|---------|--------|  
|\< 0|`string1` の部分文字列が `string2` の部分文字列より小さい。|  
|0|`string1` の部分文字列が `string2` の部分文字列と同じ。|  
|\> 0|`string1` の部分文字列が `string2` の部分文字列より大きい。|  
  
 パラメーター検証エラーが発生した場合、これらの関数は `_NLSCMPERROR` を返します。これは、\<string.h\> および \<mbstring.h\> で定義されています。  
  
## 解説  
 `_strnicmp` 関数は、`count` と `string1` の先頭の最大 `string2` 文字で序数に基づく比較を実行します。  比較は、各文字を小文字に変換することで、大文字小文字に関係なく行われます。  `_strnicmp` は `strncmp` の大文字と小文字を区別しないバージョンです。  `count` 文字を比較する前に、どちらかの文字列で終端の NULL 文字に到達すると比較は終了します。  `count` 文字を比較する前に、どちらかの文字列で終端の NULL 文字に到達したときに、文字列が等しい場合は短いほうの文字列が小さくなります。  
  
 ASCII 表の 91 から 96 の文字 \('\['、'\\'、'\]'、'^'、'\_'、および '\`'\) は、アルファベット文字より小さいものとして評価されます。  この順序付けは `stricmp` と同じです。  
  
 `_wcsnicmp` 関数と `_mbsnicmp` 関数は、`_strnicmp` 関数のワイド文字バージョンとマルチバイト文字バージョンです。  `_wcsnicmp` 関数の引数はワイド文字列で、`_mbsnicmp` 関数の引数はマルチバイト文字列です。  `_mbsnicmp` は現在のマルチバイト コード ページに基づいてマルチバイト文字のシーケンスを認識し、エラーが発生した場合は `_NLSCMPERROR` を返します  詳細については、「[コード ページ](../../c-runtime-library/code-pages.md)」を参照してください。  それ以外では、これらの関数の動作は同じです。  これらの関数はロケールの設定の影響を受けます。`_l` サフィックスが付いていないバージョンは、ロケールに依存する動作で現在のロケールを使用し、`_l` サフィックスが付いているバージョンは、渡される `locale` を代わりに使用します。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 これらのすべての関数では、パラメーターの検証が行われます。  `string1` または `string2` が null ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsncicmp`|`_strnicmp`|`_mbsnicmp`|`_wcsnicmp`|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsncicmp_l`|`_strnicmp_l`|`_mbsnicmp_l`|`_wcsnicmp_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_strnicmp`, `_strnicmp_l`|\<string.h\>|  
|`_wcsnicmp`, `_wcsnicmp_l`|\<string.h\> または \<wchar.h\>|  
|`_mbsnicmp`, `_mbsnicmp_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md) の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat、wcscat、\_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp、wcscmp、\_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strcpy、wcscpy、\_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncat、\_strncat\_l、wcsncat、\_wcsncat\_l、\_mbsncat、\_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、\_strncpy\_l、wcsncpy、\_wcsncpy\_l、\_mbsncpy、\_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strrchr、wcsrchr、\_mbsrchr、\_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset、\_strset\_l、\_wcsset、\_wcsset\_l、\_mbsset、\_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn、wcsspn、\_mbsspn、\_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)