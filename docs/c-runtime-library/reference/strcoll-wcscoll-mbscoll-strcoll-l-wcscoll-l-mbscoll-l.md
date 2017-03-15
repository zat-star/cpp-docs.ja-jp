---
title: "strcoll、wcscoll、_mbscoll、_strcoll_l、_wcscoll_l、_mbscoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcscoll"
  - "_mbscoll"
  - "_mbscoll_l"
  - "strcoll"
  - "_strcoll_l"
  - "_wcscoll_l"
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
  - "wcscoll"
  - "_mbscoll"
  - "_tcscoll"
  - "_ftcscoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コード ページ、使用 (文字列比較に)"
  - "mbscoll 関数"
  - "wcscoll_l 関数"
  - "ftcscoll 関数"
  - "wcscoll 関数"
  - "_strcoll_l 関数"
  - "tcscoll 関数"
  - "_ftcscoll 関数"
  - "_tcscoll 関数"
  - "_wcscoll_l 関数"
  - "_mbscoll 関数"
  - "strcoll_l 関数"
  - "strcoll 関数"
  - "文字列 [C++]、比較 (コード ページで)"
ms.assetid: 900a7540-c7ec-4c2f-b292-7a85f63e3fe8
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# strcoll、wcscoll、_mbscoll、_strcoll_l、_wcscoll_l、_mbscoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のロケールまたは指定された LC\_COLLATE 変換状態カテゴリを使用して、文字列を比較します。  
  
> [!IMPORTANT]
>  `_mbscoll` および `_mbscoll_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int strcoll(  
   const char *string1,  
   const char *string2   
);  
int wcscoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _strcoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale   
);  
int wcscoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale   
);  
int _mbscoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale   
);  
```  
  
#### パラメーター  
 `string1`, `string2`  
 Null で終わる比較対象の文字列。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらの各関数は、以下のように、`string1` と `string2` の関係を示す値を返します。  
  
|戻り値|string1 と string2 との関係|  
|---------|----------------------------|  
|\< 0|`string1` が `string2` より小さい|  
|0|`string1` が `string2` と同じ|  
|\> 0|`string1` が `string2` より大きい|  
  
 これらの関数はエラー発生時に `_NLSCMPERROR` を返します。  `_NLSCMPERROR` を使用するには、STRING.H または MBSTRING.H をインクルードします。  `wcscoll` は、`string1` か `string2` が NULL または照合シーケンスのドメイン外のワイド文字コードを含む場合に失敗します。  エラーが発生した場合、`wcscoll` は `EINVAL` に `errno` を設定することがあります。  `wcscoll` の呼び出し時にエラーを確認するには、`errno` を 0 に設定し、`wcscoll` を呼び出した後 `errno` をチェックします。  
  
## 解説  
 これらの各関数は、現在使用中のコード ページに基づき、大文字小文字を区別して `string1` および `string2` を比較します。  これらの関数は、現在のコード ページの文字セット順序と辞書式文字順序との間に相違点があり、この違いが文字列比較に関係がある場合にのみ使用します。  
  
 これらのすべての関数では、パラメーターの検証が行われます。  `string1` または `string2` が null ポインターの場合、または `count` が `INT_MAX` 以上の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  
  
 各ロケールには文字を並べ替えるための異なる規則があるため、2 つの文字列の比較は、ロケールに依存する操作となります。  `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のスレッドのロケールを使用します。`_l` サフィックスが付いているバージョンは、現在のロケールの代わりに渡されたロケールをパラメーターとして使用する点を除いて、対応するサフィックスなしの関数と同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcscoll`|`strcoll`|`_mbscoll`|`wcscoll`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strcoll`|\<string.h\>|  
|`wcscoll`|\<wchar.h\>、\<string.h\>|  
|`_mbscoll`, `_mbscoll_l`|\<mbstring.h\>|  
|`_strcoll_l`|\<string.h\>|  
|`_wcscoll_l`|\<wchar.h\>、\<string.h\>|  
  
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