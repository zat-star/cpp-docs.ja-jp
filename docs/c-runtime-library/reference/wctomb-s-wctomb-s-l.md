---
title: "wctomb_s、_wctomb_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wctomb_s_l"
  - "wctomb_s"
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
  - "wctomb_s"
  - "_wctomb_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wctomb_s_l 関数"
  - "文字, 変換"
  - "文字列変換, マルチバイト文字列"
  - "文字列変換, ワイド文字"
  - "wctomb_s 関数"
  - "wctomb_s_l 関数"
  - "ワイド文字, 変換"
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wctomb_s、_wctomb_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

対応するワイド文字をマルチバイト文字に変換します。  この関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[wctomb、\_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 \[出力\] `pRetValue`  
 バイト数、または結果を示すコード。  
  
 \[出力\] `mbchar`  
 マルチバイト文字のアドレス。  
  
 \[入力\] `sizeInBytes`  
 `mbchar`バッファーのサイズ。  
  
 \[入力\] `wchar`  
 ワイド文字。  
  
 \[入力\] `locale`  
 使用するロケール。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
 エラー条件  
  
|`mbchar`|`sizeInBytes`|戻り値|`pRetValue`|  
|--------------|-------------------|---------|-----------------|  
|`NULL`|\>0|`EINVAL`|変更されない|  
|任意|\>`INT_MAX`|`EINVAL`|変更されない|  
|任意|小さすぎる|`EINVAL`|変更されない|  
  
 上記のいずれかのエラー条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`wctomb` は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
## 解説  
 `wctomb_s` 関数は、対応するマルチバイト文字に `wchar` 引数を変換し、`mbchar`に結果を保存します。  プログラムの任意の場所から関数を呼び出すことができます。  
  
 `wctomb_s` マルチバイト文字にワイド文字を変換する場合、整数に `pRetValue`が指すワイド文字 \(より小さい\)、`MB_CUR_MAX`バイト数を取得します。  `wchar` はワイド文字の null 文字 \(L'\\0\) の場合、`wctomb_s` は 1.で `pRetValue` を塗りつぶします。  ターゲット `mbchar` ポインターが NULL の場合、`wctomb_s` は `pRetValue`に 0 を配置します。  変換は現在のロケールで有効でない場合、`wctomb_s` は `pRetValue`に–1 を配置します。  
  
 `wctomb_s` は ロケールに依存情報に現在のロケールを使用して; `_wctomb_s_l` は同じですが、渡されたロケールを代わりに使用します。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`wctomb_s`|\<stdlib.h\>|  
|`_wctomb_s_l`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 次のプログラムは、`wctomb` 関数の動作を示しています。  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
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