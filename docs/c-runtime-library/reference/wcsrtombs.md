---
title: "wcsrtombs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcsrtombs"
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
  - "wcsrtombs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wcsrtombs 関数"
  - "文字列変換、ワイド文字"
  - "ワイド文字、文字列"
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# wcsrtombs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチバイト文字の文字列形式にワイド文字列を変換します。  この関数のセキュリティが強化されたバージョンについては、「[wcsrtombs\_s](../../c-runtime-library/reference/wcsrtombs-s.md)」を参照してください。  
  
## 構文  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### パラメーター  
 \[出力\] `mbstr`  
 変換した結果のマルチバイト文字列のアドレス位置。  
  
 \[入力\] `wcstr`  
 間接的に変換されるワイド文字列の位置を指定します。  
  
 \[入力\] `count`  
 変換する文字数。  
  
 \[入力\] `mbstate`  
 `mbstate_t` の変換状態オブジェクトへのポインター。  
  
## 戻り値  
 エラーが発生した場合は正常に変換されていない NULL バイト \(存在する場合\)、それ以外は null を含むバイト数を返します。  
  
## 解説  
 `wcsrtombs` 関数は `mbstr`のアドレスに `wcstr`に値の間接参照先の Miter の `mbstate`に含まれている指定変換状態で始まるワイド文字列を変換します。  変換は各文字にまで続行: と終端の null ワイド文字が検出された非対応する文字に到達するまで、または次の文字が `count`に含まれている制限を超えている場合。  `wcsrtombs` はワイド文字の空白文字 `count` が発生した場合に L'\\0\) の前に発生した場合、または 8 ビット 0 に変換して停止します。  
  
 したがって、`mbstr` のマルチバイト文字列は `wcsrtombs` が変換中にワイド文字の空白文字を検出したときにのみ null で終わるです。  `wcstr` と `mbstr` が指す文字列が重なり合う場合、`wcsrtombs` 関数の動作は未定義です。  `wcsrtombs` は 現在のロケールで LC\_TYPE のカテゴリ別に影響されます。  
  
 `wcsrtombs` 関数は restartability で [wcstombs、\_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md) とは異なります。  変換状態は同じまたは別の restartable 関数への後続の呼び出しの `mbstate` に格納されます。  結果は restartable と nonrestartable 関数の使用を混在させると undefined になります。たとえば、アプリケーションが `wcsnlen`ではなく `wcsrtombs` への以降の呼び出しが `wcstombs`の代わりに使用すると、`wcsrlen` を使用します。  
  
 `mbstr` の引数が `NULL`の場合、`wcsrtombs` はコピー先文字列のバイトの必要なサイズを返します。  `mbstate` が NULL の場合、`mbstate_t` 変換の内部状態が使用されます。  文字列 `wchar` に対応するマルチバイト文字表現が見つからなかった場合は、戻り `errno` は `EILSEQ`に設定されます。  
  
 C\+\+ では、この関数によって新しい呼び出すのテンプレート オーバーロードが、保護されたこの関数に対応するが含まれます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
## 例外  
 `wcsrtombs` 関数は、関数が実行中、`mbstate` が NULL ではなく、現在のスレッドの関数が `setlocale` を呼び出さない限りマルチスレッド セーフです。  
  
## 使用例  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
  **文字列が正常に変換されました。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`wcsrtombs`|\<wchar.h\>|  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb、\_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs、\_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)