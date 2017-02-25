---
title: "_strninc、_wcsninc、_mbsninc、_mbsninc_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsninc"
  - "_mbsninc_l"
  - "_wcsninc"
  - "_strninc"
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
  - "strninc"
  - "wcsninc"
  - "mbsninc_l"
  - "_strninc"
  - "_tcsninc"
  - "mbsninc"
  - "_mbsninc_l"
  - "_ftcsninc"
  - "_wcsninc"
  - "_mbsninc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsninc 関数"
  - "_mbsninc_l 関数"
  - "_strninc 関数"
  - "_tcsninc 関数"
  - "_wcsninc 関数"
  - "mbsninc 関数"
  - "mbsninc_l 関数"
  - "strninc 関数"
  - "tcsninc 関数"
  - "wcsninc 関数"
ms.assetid: 6caace64-f9e4-48c0-afa8-ea51824ad723
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _strninc、_wcsninc、_mbsninc、_mbsninc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列ポインターを `n` 個進めます。  
  
> [!IMPORTANT]
>  `_mbsninc` および `_mbsninc_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
char *_strninc(  
   const char *str,  
   size_t count   
);  
wchar_t *_wcsninc(  
   const wchar_t *str,  
   size_t count   
);  
unsigned char *_mbsninc(  
   const unsigned char *str,  
   size_t count   
);  
unsigned char *_mbsninc(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `str`  
 ソース文字列。  
  
 `count`  
 文字列ポインターをインクリメントする文字数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらの各ルーチンは、指定されたポインターが `NULL` の場合に `str` が `count` または `NULL` によってインクリメントされた後、`str` のポインターを返します。  `count` が `str` の文字数以上の場合、結果は未定義になります。  
  
## 解説  
 `_mbsninc` 関数は `count` のマルチバイト文字で `str` をインクリメントします。  `_mbsninc` 関数は、現在使用中の[マルチバイト コード ページ](../../c-runtime-library/code-pages.md)に基づいて、マルチバイト文字列を認識します。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsninc`|`_strninc`|`_mbsninc`|`_wcsninc`|  
  
 `_strninc` と `_wcsninc` はそれぞれ、`_mbsninc` の 1 バイト文字列バージョンとワイド文字列バージョンです。  `_wcsninc` と `_strninc` はこの割り当てにのみ使用し、それ以外には使用しないでください。  詳細については、「[汎用テキスト マップの使用](../../c-runtime-library/using-generic-text-mappings.md)」および「[汎用テキスト マップ](../../c-runtime-library/generic-text-mappings.md)」を参照してください。  
  
 `_mbsninc_l` は、代わりに渡されるロケール パラメーターを使用することを除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_mbsninc`|\<mbstring.h\>|  
|`_mbsninc_l`|\<mbstring.h\>|  
|`_strninc`|\<tchar.h\>|  
|`_wcsninc`|\<tchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strdec、\_wcsdec、\_mbsdec、\_mbsdec\_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [\_strinc、\_wcsinc、\_mbsinc、\_mbsinc\_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [\_strnextc、\_wcsnextc、\_mbsnextc、\_mbsnextc\_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)