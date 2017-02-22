---
title: "_mbsnbcoll、_mbsnbcoll_l、_mbsnbicoll、_mbsnbicoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbicoll_l"
  - "_mbsnbcoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
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
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbicoll"
  - "mbsnbcoll"
  - "mbsnbicoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
  - "_ftcsnicoll"
  - "_ftcsncoll"
  - "mbsnbcoll_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcoll 関数"
  - "_mbsnbcoll_l 関数"
  - "_mbsnbicoll 関数"
  - "_mbsnbicoll_l 関数"
  - "_tcsncoll 関数"
  - "_tcsnicoll 関数"
  - "mbsnbcoll 関数"
  - "mbsnbcoll_l 関数"
  - "mbsnbicoll 関数"
  - "mbsnbicoll_l 関数"
  - "tcsncoll 関数"
  - "tcsnicoll 関数"
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _mbsnbcoll、_mbsnbcoll_l、_mbsnbicoll、_mbsnbicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチバイト コード ページの情報を使用して、2 つのマルチバイト文字列の `n` バイトを比較します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _mbsnbcoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnbicoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `string1, string2`  
 比較する文字列。  
  
 `count`  
 比較するバイト数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 戻り値は `string1` と `string2`の部分文字列の関係を示します。  
  
|戻り値|説明|  
|---------|--------|  
|\< 0|`string1` の部分文字列が `string2` の部分文字列より小さい。|  
|0|`string2` の部分文字列は `string1` の部分文字列と同じ。|  
|\> 0|`string1` の部分文字列が `string2` の部分文字列より大きい。|  
  
 `string1` または `string2` が `NULL` の場合、または `count` が `INT_MAX` を超える場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  `_NLSCMPERROR` を使用するには、String.h または Mbstring.h をインクルードします。  
  
## 解説  
 これらの関数は、最長で `string1` と `string2` の先頭 `count` バイトを比較し、得られた `string1` の部分文字列と `string2` の部分文字列の関係を示す値を返します。  `string1` または `string2` の部分文字列の最後のバイトが先行バイトの場合、比較に含まれません。これらの関数は、部分文字列の完全な文字だけを比較します。  `_mbsnbicoll` は `_mbsnbcoll` の大文字と小文字を区別しないバージョンです。  `_mbsnbcmp` と `_mbsnbicmp` のように、`_mbsnbcoll` と `_mbsnbicoll` は、現在使用中のマルチバイト [コード ページ](../../c-runtime-library/code-pages.md)で指定された辞書式の順序に従って 2 個のマルチバイト文字列を照合します。  
  
 一部のコード ページおよびそれに対応する文字セットでは、文字セットの文字の順序が辞書式の順序と異なる場合があります。  "C" ロケールでは、前述とは異なり、ASCII 文字セットの文字の順序が辞書式の文字の順序と同じです。  しかし、たとえば、ヨーロッパの一部のコード ページでは、文字 a \(値 0x61\) は文字セットで文字 'ä' \(値 0xE4\) の前にありますが、辞書式の順序では文字 'ä' が文字 'a' の前にあります。  このような場合にバイトの文字列の辞書式の比較を実行するには、`_mbsnbcmp` ではなく `_mbsnbcoll` を使用してください。文字列の等価性のみを検証するには、`_mbsnbcmp` を使用します。  
  
 `cmp` 関数が単に文字列の等価性をテストするのに対して、`coll` 関数は比較のために文字列を辞書式に照合するため、`coll` 関数は `cmp` の対応するバージョンよりもかなり低速です。  したがって、`coll` 関数は、現在のコード ページの文字セット順序と辞書式文字順序との間に相違点あり、この違いが比較に関係がある場合にのみ使用します。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないこの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsncoll`|[\_strncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll`|[\_wcsncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsncoll_l`|[\_strncoll、\_wcsncoll、\_mbsncoll、\_strncoll\_l、\_wcsncoll\_l、\_mbsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll_l`|[\_wcsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsnicoll`|[\_strnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll`|[\_wcsnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
|`_tcsnicoll_l`|[\_strnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll_l`|[\_wcsnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_mbsnbcoll`|\<mbstring.h\>|  
|`_mbsnbcoll_l`|\<mbstring.h\>|  
|`_mbsnbicoll`|\<mbstring.h\>|  
|`_mbsnbicoll_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat、\_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbcmp、\_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_mbsnbicmp、\_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)