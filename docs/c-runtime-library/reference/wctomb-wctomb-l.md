---
title: "wctomb、_wctomb_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wctomb_l"
  - "wctomb"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wctomb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctomb_l 関数"
  - "文字, 変換"
  - "文字列変換, マルチバイト文字列"
  - "文字列変換, ワイド文字"
  - "wctomb 関数"
  - "wctomb_l 関数"
  - "ワイド文字, 変換"
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# wctomb、_wctomb_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

対応するワイド文字をマルチバイト文字に変換します。  これらの関数のセキュリティを強化したバージョンについては、「[wctomb\_s、\_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)」を参照してください。  
  
## 構文  
  
```  
int wctomb(  
   char *mbchar,  
   wchar_t wchar   
);  
int _wctomb_l(  
   char *mbchar,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `mbchar`  
 マルチバイト文字のアドレス。  
  
 `wchar`  
 ワイド文字。  
  
## 戻り値  
 `wctomb` マルチバイト文字にワイド文字を変換する場合、\(より小さい\)、`MB_CUR_MAX`ワイド文字のバイト数を返します。  `wchar` はワイド文字の null 文字 \(L'\\0\) の場合、`wctomb` を返します。1.  ターゲット `mbchar` ポインターが NULL の場合、`wctomb` 0 を返します。  変換は現在のロケールで有効でない場合、`wctomb` は–1 を返し、`errno` は `EILSEQ`に設定されます。  
  
## 解説  
 `wctomb` 関数は、対応するマルチバイト文字に `wchar` 引数を変換し、`mbchar`に結果を保存します。  プログラムの任意の場所から関数を呼び出すことができます。  `wctomb` は、すべてのロケールに依存する動作に現在のロケールを使用します。`_wctomb_l` は、渡されたロケールを代わりに使用することを除いて`wctomb` と同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `wctomb` はそのパラメーターを検証します。  `mbchar` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続 `errno` は `EINVAL` および関数の戻り値が \-1 に設定されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`wctomb`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 このプログラムは、wctomb 関数の動作を示しています。  
  
```  
// crt_wctomb.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int i;  
   wchar_t wc = L'a';  
   char *pmb = (char *)malloc( MB_CUR_MAX );  
  
   printf( "Convert a wide character:\n" );  
   i = wctomb( pmb, wc ); // C4996  
   // Note: wctomb is deprecated; consider using wctomb_s  
   printf( "   Characters converted: %u\n", i );  
   printf( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
  **ワイド文字を変換する:**  
 **変換された文字: 1**  
 **マルチバイト文字: a**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [\_mbclen、mblen、\_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs、\_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc、\_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)   
 [wcstombs、\_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)