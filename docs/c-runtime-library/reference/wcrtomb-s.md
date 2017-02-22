---
title: "wcrtomb_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcrtomb_s"
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
  - "wcrtomb_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ワイド文字を変換します。"
  - "wcrtomb_s 関数"
  - "マルチバイト文字"
  - "変換する文字"
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# wcrtomb_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ワイド文字をマルチバイト文字の表現に変換します。 バージョンの [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) 」の説明に従って、セキュリティ強化機能を備えた [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)します。  
  
## 構文  
  
```  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char *mbchar,  
   size_t sizeOfmbchar,  
   wchar_t *wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char (&mbchar)[size],  
   wchar_t *wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### パラメーター  
 \[出力\] `pReturnValue`  
 エラーが発生した場合は、書き込まれたバイト数または\-1 を返します。  
  
 \[出力\] `mbchar`  
 結果として得られるマルチバイトに変換された文字を指定します。  
  
 \[入力\] `sizeOfmbchar`  
 サイズ、 `mbchar` 変数 \(バイト単位\)。  
  
 \[入力\] `wchar`  
 変換するワイド文字。  
  
 \[入力\] `mbstate`  
 `mbstate_t` オブジェクトへのポインター。  
  
## 戻り値  
 0 を返すまたは `errno` 値の場合は、エラーが発生します。  
  
## 解説  
 `wcrtomb_s` 関数以降に含まれる指定された変換の状態で、ワイド文字に変換 `mbstate`, に格納された値から `wchar`, 、によって表されるアドレスに `mbchar`します。`pReturnValue` 値が変換されると、バイトの数になる複数の `MB_CUR_MAX` バイト、またはエラーが発生した場合、\-1 です。  
  
 場合 `mbstate` が null の場合、内部 `mbstate_t` 変換状態を使用します。 文字が含まれる場合 `wchar` 対応するマルチバイト文字の値を持たない `pReturnValue` は\-1 になり、関数は、 `errno` の値 `EILSEQ`です。  
  
 `wcrtomb_s` 関数とは異なります [wctomb\_s、\_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) によってその再起動します。 同じ関数または再開可能な他の関数の後続の呼び出しのために、変換状態が `mbstate` に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは使用 `wcsrlen` なく `wcslen`, 場合、後続の呼び出しには、 `wcsrtombs_s` の代わりに使用されました。 `wcstombs_s.`  
  
 C\+\+ では、この関数を簡単に使用してテンプレートのオーバー ロードオーバー ロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要はありません\)、古くてセキュリティが保護されていない機能、セキュリティで保護された新しいバージョンに自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
## 例外  
 `wcrtomb_s` 関数は、呼び出す関数は、現在のスレッドがない限り、マルチ スレッド セーフ `setlocale` この関数の実行中に、 `mbstate` が null です。  
  
## 使用例  
  
```  
// crt_wcrtomb_s.c  
// This program converts a wide character  
// to its corresponding multibyte character.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    errno_t     returnValue;  
    size_t      pReturnValue;  
    mbstate_t   mbstate;  
    size_t      sizeOfmbStr = 1;  
    char        mbchar = 0;  
    wchar_t*    wchar = L"Q\0";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),  
                            *wchar, &mbstate);  
    if (returnValue == 0) {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wchar);  
        printf(" was converted to a the \"%c\" ", mbchar);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
```Output  
対応するワイド文字"Q"が変換された、"Q"マルチバイト文字。  
```  
  
## 同等の .NET Framework 関数  
 該当しない。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`wcrtomb_s`|\<wchar.h\>|  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)