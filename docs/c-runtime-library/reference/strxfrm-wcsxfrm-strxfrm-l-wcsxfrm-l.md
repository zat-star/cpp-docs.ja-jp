---
title: "strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strxfrm"
  - "_wcsxfrm_l"
  - "_strxfrm_l"
  - "wcsxfrm"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strxfrm"
  - "_tcsxfrm"
  - "wcsxfrm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strxfrm_l 関数"
  - "_tcsxfrm 関数"
  - "_wcsxfrm_l 関数"
  - "文字列比較 [C++], 変換 (文字列を)"
  - "文字列 [C++], 比較 (ロケールを)"
  - "strxfrm 関数"
  - "strxfrm_l 関数"
  - "tcsxfrm 関数"
  - "wcsxfrm 関数"
  - "wcsxfrm_l 関数"
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ロケール固有の情報に基づいて、文字列を変換します。  
  
## 構文  
  
```  
size_t strxfrm(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
size_t wcsxfrm(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
size_t _strxfrm_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
size_t wcsxfrm_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `strDest`  
 対象文字列。  
  
 `strSource`  
 ソース文字列。  
  
 `count`  
 `strDest` に指定する最大文字数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 変換された文字列の長さを返します。終端の NULL 文字は数えません。  戻り値が `count` の文字数以上の場合、`strDest` の内容は予測できません。  エラーが発生すると、各関数は `errno` を設定し、`INT_MAX` を返します。  無効な文字に対し、`errno` は `EILSEQ` に設定されます。  
  
## 解説  
 `strxfrm` 関数は、`strSource` が指す文字列を新しい照合形式に変換し、`strDest` に格納します。  NULL 文字を含めて `count` で指定する文字数までが変換され、結果の文字列として格納されます。  変換は、ロケールの `LC_COLLATE` カテゴリの設定に基づいて行われます。  `LC_COLLATE` の詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `strxfrm` は、ロケールに依存する動作に現在のロケールを使用します。`_strxfrm_l` は、現在のロケールではなく渡されたロケールを使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 変換後、2 つの変換済み文字列を指定して `strcmp` 関数を呼び出すと、変換前の 2 つの文字列を指定して `strcoll` 関数を呼び出したときと同じ結果になります。  `strcoll` 関数や `stricoll` 関数と同様に、`strxfrm` 関数は、マルチバイト文字列を適切に処理します。  
  
 `wcsxfrm` は `strxfrm` のワイド文字バージョンであり、`wcsxfrm` の文字列引数はワイド文字ポインターです。  `wcsxfrm` の場合、文字列の変換後に、2 つの変換した文字列を使用して `wcscmp` を呼び出すと、元の 2 つの文字列に適用する `wcscoll` を呼び出したときと同じ結果になります。  それ以外では、`wcsxfrm` と `strxfrm` の動作は同じです。  `wcsxfrm` は、ロケールに依存する動作に現在のロケールを使用します。`_wcsxfrm_l` は、現在のロケールではなく渡されたロケールを使用する点を除いて同じです。  
  
 これらの関数では、パラメーターの検証が行われます。  `strSource` が null ポインターの場合、`strDest` が null ポインターの場合 \(カウントが 0 でなければ\)、または `count` が `INT_MAX` より大きい場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`INT_MAX` を返します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcsxfrm`|`strxfrm`|`strxfrm`|`wcsxfrm`|  
|`_tcsxfrm_l`|`_strxfrm_l`|`_strxfrm_l`|`_wcsxfrm_l`|  
  
 "C" ロケールでは、文字セット \(ASCII 文字セット\) の文字の順序が辞書式の文字の順序と同じです。  ただし、文字セットの文字の順序が辞書式の順序と異なるロケールもあります。  たとえば、特定のヨーロッパのロケールでは、文字「a」 \(値 0x61\) は文字 '&\#x00E4 に先行します; 」 \(値 0xE4\) 文字セット、文字「ä で辞書式に、文字「a」の"。  
  
 文字セットの順序が辞書式の順序と異なるロケールでは、元の文字列で `strxfrm` 関数を実行してから、結果の文字列で `strcmp` 関数を使用して、現在のロケールの `LC_COLLATE` カテゴリの設定に基づいた辞書式の文字列比較を行います。  したがって、上記のヨーロッパのロケールで 2 つの文字列を辞書式に比較するには、元の文字列で `strxfrm` 関数を使用してから、結果の文字列で `strcmp` 関数を使用します。  また、元の文字列で `strcmp` 関数ではなく `strcoll` 関数を使用することもできます。  
  
 `strxfrm` は基本的に、`LCMAP_SORTKEY` を持つ [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) のラッパーです。  
  
 次の式の値は、`strxfrm` 関数で元の文字列を変換した結果の保持に必要な配列のサイズです。  
  
```  
1 + strxfrm( NULL, string, 0 )  
```  
  
 `strxfrm` 関数は、"C" ロケールでのみ以下と同等です。  
  
```  
strncpy( _string1, _string2, _count );  
return( strlen( _string1 ) );  
```  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strxfrm`|\<string.h\>|  
|`wcsxfrm`|\<string.h\> または \<wchar.h\>|  
|`_strxfrm_l`|\<string.h\>|  
|`_wcsxfrm_l`|\<string.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [strcmp、wcscmp、\_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)