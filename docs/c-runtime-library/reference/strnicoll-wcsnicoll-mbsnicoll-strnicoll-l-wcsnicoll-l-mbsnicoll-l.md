---
title: "_strnicoll、_wcsnicoll、_mbsnicoll、_strnicoll_l、_wcsnicoll_l、_mbsnicoll_l | Microsoft Docs"
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
  - "_mbsnicoll_l"
  - "_mbsnicoll"
  - "_wcsnicoll_l"
  - "_strnicoll"
  - "_strnicoll_l"
  - "_wcsnicoll"
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
  - "wcshicoll_l"
  - "_ftcsncicoll"
  - "strnicoll_l"
  - "_wcsnicoll"
  - "mbsnicoll_l"
  - "_strnicoll"
  - "mbsnicoll"
  - "_ftcsnicoll"
  - "wcsnicoll"
  - "_tcsnicoll"
  - "_mbsnicoll"
  - "strinicoll"
  - "_tcsncicoll"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsncicoll 関数"
  - "_ftcsnicoll 関数"
  - "_mbsnicoll 関数"
  - "_mbsnicoll_l 関数"
  - "_strnicoll 関数"
  - "_strnicoll_l 関数"
  - "_tcsncicoll 関数"
  - "_tcsnicoll 関数"
  - "_wcsnicoll 関数"
  - "_wcsnicoll_l 関数"
  - "コード ページ, 使用 (文字列比較に)"
  - "ftcsncicoll 関数"
  - "ftcsnicoll 関数"
  - "mbsnicoll 関数"
  - "mbsnicoll_l 関数"
  - "文字列 [C++], 比較 (コード ページで)"
  - "strnicoll 関数"
  - "strnicoll_l 関数"
  - "tcsncicoll 関数"
  - "tcsnicoll 関数"
  - "wcsnicoll 関数"
  - "wcsnicoll_l 関数"
ms.assetid: abf0c569-725b-428d-9ff2-924f430104b4
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strnicoll、_wcsnicoll、_mbsnicoll、_strnicoll_l、_wcsnicoll_l、_mbsnicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ロケール固有の情報を使用して文字列を比較します。  
  
> [!IMPORTANT]
>  `_mbsnicoll` および `_mbsnicoll_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _strnicoll(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsnicoll(  
   const wchar_t *string1,  
   const wchar_t *string2 ,  
   size_t count   
);  
int _mbsnicoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strnicoll_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsnicoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2 ,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `string1, string2`  
 Null で終わる比較対象の文字列  
  
 `count`  
 比較する文字数  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらの関数は、以下のように、`string1` と `string2` の部分文字列の関係を示す値を返します。  
  
|戻り値|string1 と string2 との関係|  
|---------|----------------------------|  
|\< 0|`string1` が `string2` より小さい|  
|0|`string1` が `string2` と同じ|  
|\> 0|`string1` が `string2` より大きい|  
  
 これらの各関数は、`_NLSCMPERROR` を返します。  `_NLSCMPERROR` を使用するには、STRING.H または MBSTRING.H をインクルードします。  `_wcsnicoll` は、`string1` か `string2` に照合シーケンスのドメイン外のワイド文字コードが含まれている場合に失敗します。  エラーが発生した場合、`_wcsnicoll` は `EINVAL` に `errno` を設定することがあります。  `_wcsnicoll` の呼び出し時にエラーを確認するには、`errno` を 0 に設定し、`_wcsnicoll` を呼び出した後 `errno` をチェックします。  
  
## 解説  
 これらの関数はコード ページに従って `string1` と `string2` の最初の `count` 文字を大文字と小文字を区別せずに比較します。  これらの関数は、コード ページの文字セット順序と辞書式文字順序との間に相違点あり、この違いが文字列比較に関係がある場合にのみ使用します。  `_l` のサフィックスのないこれらの関数の各バージョンは、現在のロケールとコード ページを使用します。  `_l` のサフィックスのある各バージョンは、代わりに渡されたロケールを使用することを除き、同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 これらのすべての関数では、パラメーターの検証が行われます。  `string1` または `string2` が null ポインターの場合、または count が `INT_MAX` を超える場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `_NLSCMPERROR` を返し、`errno` に `EINVAL` を設定します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcsncicoll`|`_strnicoll`|`_mbsnbicoll`|`_wcsnicoll`|  
|`_tcsnicoll`|`_strnicoll`|[\_mbsnbicoll](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|`_wcsnicoll`|  
|`_tcsnicoll_l`|`_strnicoll_l`|`_mbsnbicoll_l`|`_wcsnicoll_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_strnicoll`, `_strnicoll_l`|\<string.h\>|  
|`_wcsnicoll`, `_wcsnicoll_l`|\<wchar.h\> または \<string.h\>|  
|`_mbsnicoll`, `_mbsnicoll_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## 参照  
 [ロケール](../../c-runtime-library/locale.md)   
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll、\_mbsnbcoll\_l、\_mbsnbicoll、\_mbsnbicoll\_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [strcmp、wcscmp、\_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [\_stricmp、\_wcsicmp、\_mbsicmp、\_stricmp\_l、\_wcsicmp\_l、\_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm、wcsxfrm、\_strxfrm\_l、\_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)