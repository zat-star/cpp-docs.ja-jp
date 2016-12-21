---
title: "wcsrtombs_s | Microsoft Docs"
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
  - "wcsrtombs_s"
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
  - "wcsrtombs_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "文字列変換, ワイド文字"
  - "wcsrtombs_s 関数"
  - "ワイド文字, 文字列"
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: 27
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcsrtombs_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチバイト文字の文字列形式にワイド文字列を変換します。  この関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### パラメーター  
 \[出力\] `pReturnValue`  
 変換された文字数。  
  
 \[出力\] `mbstr`  
 変換結果のマルチバイト文字列用のバッファーのアドレス。  
  
 \[出力\] `sizeInBytes`  
 `mbstr` バッファーのサイズ \(バイト数\)。  
  
 \[入力\] `wcstr`  
 変換されるワイド文字列を指します。  
  
 \[入力\] `count`  
 `mbstr` バッファーに格納される最大バイト数または [\_TRUNCATE](../../c-runtime-library/truncate.md)。  
  
 \[入力\] `mbstate`  
 `mbstate_t` の変換状態オブジェクトへのポインター。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
|エラー条件|戻り値と `errno`|  
|-----------|------------------|  
|`mbstr` は `NULL` と `sizeInBytes` \> 0 です。|`EINVAL`|  
|`wcstr` が `NULL` です。|`EINVAL`|  
|変換先バッファーが小さいため変換後の文字列が収まらない \(`count` が `_TRUNCATE` の場合は例外。下記の「解説」を参照\)|`ERANGE`|  
  
 上記のいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーターの例外が呼び出されます。  実行の続行が許可された場合、関数はエラー コードを返し、`errno` を表で示されている値に設定します。  
  
## 解説  
 `wcsrtombs_s` 関数は `mbstate`に含まれる変換状態を使用して `mbstr`によって指されるバッファーに格納されているマルチバイト文字に `wcstr` が指すワイド文字列を変換します。  変換は各文字列に対して行われ、次の条件の 1 つが満たされるまで続行されます。  
  
-   null ワイド文字が検出された  
  
-   変換できないワイド文字が検出された  
  
-   `mbstr` バッファーに格納されたバイト数が `count` と等しい。  
  
 変換後の文字列は、常に null で終わります \(エラーの場合も同様\)。  
  
 `count` が特殊な値 [\_TRUNCATE](../../c-runtime-library/truncate.md)の場合、`wcsrtombs_s` は、null 終端文字の空きを残して変換先バッファーに収まるように文字列と変換を行います。  
  
 `wcsrtombs_s` は、変換元の文字列の変換に成功すると、null 終端文字を含む変換した文字列のサイズ \(バイト単位\) を `*``pReturnValue` に設定します \(`pReturnValue` が `NULL` でない場合\)。  これは、`mbstr` 引数が `NULL` の場合でも発生するので、これを使用して必要なバッファー サイズを確認できます。  `mbstr` が `NULL` の場合、`count` は無視されます。  
  
 `wcsrtombs_s` マルチバイト文字に変換できないワイド文字を検出 `*``pReturnValue`に \-1 を配置し、空の文字列に変換先バッファーを設定し、`EILSEQ`に `errno` を設定し、`EILSEQ`を返します。  
  
 `wcstr` と `mbstr` が指す文字列が重なり合う場合、`wcsrtombs_s` 関数の動作は未定義です。  `wcsrtombs_s` は 現在のロケールで LC\_TYPE のカテゴリ別に影響されます。  
  
> [!IMPORTANT]
>  `wcstr` と `mbstr` が重なり合っていないこと、`count` が変換対象のワイド文字数を正しく反映していることを確認してください。  
  
 `wcsrtombs_s` 関数は restartability で [wcstombs\_s、\_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md) とは異なります。  変換状態は同じまたは別の restartable 関数への後続の呼び出しの `mbstate` に格納されます。  結果は restartable と nonrestartable 関数の使用を混在させると undefined になります。  たとえば、アプリケーションが `wcslen`ではなく `wcsrtombs_s` への以降の呼び出しが `wcstombs_s.`の代わりに使用すると、`wcsrlen` を使用します。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
## 例外  
 `wcsrtombs_s` 関数は、関数が実行中、`mbstate` が null で、現在のスレッドの関数が `setlocale` を呼び出さない限りマルチスレッド セーフです。  
  
## 使用例  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
  **文字列が正常に変換されました。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`wcsrtombs_s`|\<wchar.h\>|  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb、\_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs、\_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)