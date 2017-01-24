---
title: "wcrtomb | Microsoft Docs"
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
  - "wcrtomb"
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
  - "wcrtomb"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "文字, 変換"
  - "マルチバイト文字"
  - "wcrtomb 関数"
  - "ワイド文字, 変換"
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcrtomb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチバイト文字表現にワイド文字を変換します。  この関数のセキュリティが強化されたバージョンについては、「[wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)」を参照してください。  
  
## 構文  
  
```  
size_t wcrtomb(  
   char *mbchar,  
   wchar_t wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcrtomb(  
   char (&mbchar)[size],  
   wchar_t wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### パラメーター  
 \[出力\] `mbchar`  
 結果のマルチバイト文字に変換できます。  
  
 \[入力\] `wchar`  
 変換されるワイド文字。  
  
 \[入力\] `mbstate`  
 `mbstate_t` オブジェクトへのポインター。  
  
## 戻り値  
 エラーが発生した場合に変換した場合は、マルチバイト文字を表すために必要なバイト数を返します。  
  
## 解説  
 `wcrtomb` 関数は `mbchar`で表されるアドレスに `wchar`に含まれる値の `mbstate`に含まれている指定変換状態で始まるワイド文字を変換します。  戻り値は、対応するマルチバイト文字を表すために必要なバイト数が `MB_CUR_MAX` バイトよりも返されます。  
  
 `mbstate` が NULL の場合、`mbstate_t` などの内部オブジェクトは `mbchar` の変換状態が使用されます。  文字列 `wchar` に対応するマルチバイト文字表現が見つからなかった場合は、戻り `errno` は `EILSEQ`に設定されます。  
  
 `wcrtomb` 関数は restartability で [wctomb、\_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) とは異なります。  変換状態は同じまたは別の restartable 関数への後続の呼び出しの `mbstate` に格納されます。  結果は restartable と nonrestartable 関数の使用を混在させると undefined になります。  たとえば、アプリケーションが `wcsnlen`ではなく `wcsrtombs` への以降の呼び出しが `wcstombs`の代わりに使用すると、`wcsrlen` を使用します。  
  
 C\+\+ では、この関数によって新しい呼び出すのテンプレート オーバーロードが、保護されたこの関数に対応するが含まれます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
## 例外  
 `wcrtomb` 関数は、関数の実行中に、`mbstate` が null のときに、現在のスレッドの関数が `setlocale` を呼び出さない限りマルチスレッド セーフです。  
  
## 使用例  
  
```  
// crt_wcrtomb.c  
// compile with: /W3  
// This program converts a wide character  
// to its corresponding multibyte character.  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    size_t      sizeOfCovertion = 0;  
    mbstate_t   mbstate;  
    char        mbStr = 0;  
    wchar_t*    wcStr = L"Q";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996  
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead  
    if (sizeOfCovertion > 0)  
    {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wcStr);  
        printf(" was converted to the \"%c\" ", mbStr);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
  **対応するワイド文字は「Q」Q」マルチバイト文字に変換されます。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`wcrtomb`|\<wchar.h\>|  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)