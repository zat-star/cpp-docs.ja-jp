---
title: "strcoll 系関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strcoll"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "コード ページ, 使用 (文字列比較に)"
  - "strcoll 関数"
  - "文字列比較 [C++], カルチャ固有の"
  - "文字列 [C++], 比較 (コード ページで)"
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strcoll 系関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`strcoll` と `wcscoll` の各関数は、現在使用中のロケールのコード ページの `LC_COLLATE` カテゴリの設定に基づいて、2 文字列を比較します。  `_mbscoll` の関数は、現在使用中のマルチバイト コード ページに従って 2 桁の文字列を比較します。  文字セットの順序は、現在のコード ページの辞書式の順序とこの相違点の違いを比較の対象である場合文字列比較に `coll` 関数を使用します。  文字列が等しいかどうかのみをテストするために `cmp` の対応する関数を使用します。  
  
### 系関数  
  
|SBCS|Unicode|MBCS|説明|  
|----------|-------------|----------|--------|  
|[系](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[\_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|2 桁の文字列を照合します。|  
|[\_stricoll](../Topic/_stricoll,%20_wcsicoll,%20_mbsicoll,%20_stricoll_l,%20_wcsicoll_l,%20_mbsicoll_l.md)|[\_wcsicoll](../Topic/_stricoll,%20_wcsicoll,%20_mbsicoll,%20_stricoll_l,%20_wcsicoll_l,%20_mbsicoll_l.md)|[\_mbsicoll](../Topic/_stricoll,%20_wcsicoll,%20_mbsicoll,%20_stricoll_l,%20_wcsicoll_l,%20_mbsicoll_l.md)|照合します。2 の文字列 \(大文字と小文字を区別しない\) を|  
|[\_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|2 番目の文字列の `count` の最初の文字を照合します。|  
|[\_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|照合します。2 の文字列 \(大文字と小文字を区別しない\) の `count` の最初の文字を|  
  
## 解説  
 これらの関数 \(`strcoll`、`stricoll`、`_strncoll`と `_strnicoll`\) のバイト文字 \(SBCS\) のバージョンは、現在のロケールの `LC_COLLATE` カテゴリの設定に基づいて `string1``string2` とを比較します。  これらの関数は `strcmp` の対応する関数と `strcoll` 関数が照合順序を提供するロケールのコード ページ情報を使用することです。  文字セットの順序が辞書式の順序と異なるロケールの文字列比較では、`strcoll` 関数は `strcmp` の対応する関数の代わりに使用する必要があります。  `LC_COLLATE` の詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  
  
 対応するコード ページと文字セットでは、文字セットの文字の順序が辞書式の順序と異なることがあります。  "C" ロケールでは、前述とは異なり、ASCII 文字セットの文字の順序が辞書式の文字の順序と同じです。  しかし、たとえば、ヨーロッパの一部のコード ページでは、文字 a \(値 0x61\) は文字セットで文字 'ä' \(値 0xE4\) の前にありますが、辞書式の順序では文字 'ä' が文字 'a' の前にあります。  このようなインスタンスで辞書式の比較を実行するには、`strcmp`ではなく `strcoll` を使用します。  また、元の文字列の `strxfrm` を使用し、結果の文字列の `strcmp` を使用します。  
  
 ワイド文字 \(Unicode\) に対応するように`strcoll`、`stricoll`、`_strncoll`と `_strnicoll` は、現在使用中のロケールのコード ページに従ってマルチバイト文字列を自動的に処理します。  ただし、これらの関数のマルチバイト文字の \(MBCS\) Version は、現在使用中のマルチバイト コード ページに従ってマルチバイト文字単位で文字列を照合します。  
  
 `cmp` 関数が単に文字列の等価性をテストするのに対して、`coll` 関数は比較のために文字列を辞書式に照合するため、`coll` 関数は `cmp` の対応するバージョンよりもかなり低速です。  したがって、`coll` 関数は、文字セットの順序は、現在のコード ページの辞書式の順序とこの相違点の違いを文字列比較のターゲットである場合のみ使用します。  
  
## 参照  
 [ロケール](../c-runtime-library/locale.md)   
 [文字列操作](../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll、\_mbsnbcoll\_l、\_mbsnbicoll、\_mbsnbicoll\_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [strcmp、wcscmp、\_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm、wcsxfrm、\_strxfrm\_l、\_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)