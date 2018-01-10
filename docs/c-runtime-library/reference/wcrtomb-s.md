---
title: wcrtomb_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcrtomb_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords: wcrtomb_s
dev_langs: C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13134a3e6b34be13d6d878cf94f204bb6c87a458
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="wcrtombs"></a>wcrtomb_s
ワイド文字をマルチバイト文字の表現に変換します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) です。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pReturnValue`  
 書き込まれたバイト数を返します。エラーが発生した場合は -1 を返します。  
  
 [出力] `mbchar`  
 結果として得られるマルチバイトに変換された文字。  
  
 [入力] `sizeOfmbchar`  
 `mbchar` 変数のサイズ (バイト単位)。  
  
 [入力] `wchar`  
 変換するワイド文字。  
  
 [入力] `mbstate`  
 `mbstate_t` オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 0、またはエラーが発生した場合は `errno` 値を返します。  
  
## <a name="remarks"></a>コメント  
 `wcrtomb_s` 関数は、`mbstate` に含まれる指定された変換の状態で始まるワイド文字を、`wchar` に含まれている値から、`mbchar` によって表されるアドレスに変換します。 `pReturnValue` 値は変換されたバイト数になりますが、`MB_CUR_MAX` バイトより多くはなりません。エラーが発生した場合は、-1 が返されます。  
  
 `mbstate` が null の場合、内部の `mbstate_t` 変換状態が使用されます。 `wchar` に含まれる文字が対応するマルチバイト文字の値を持たない場合、`pReturnValue` の値は -1 になり、関数は `EILSEQ` の `errno` 値を返します。  
  
 `wcrtomb_s` 関数は、再開できるかどうかの点で [wctomb_s、_wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) と異なります。 同じ関数または再開可能な他の関数の後続の呼び出しのために、変換状態が `mbstate` に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは `wcsrlen` を使用し、`wcslen` は使用しないことがあります。これは、後続の呼び出しで `wcsrtombs_s` を使用しており、`wcstombs_s.` は使用しない場合です。  
  
 C++ では、この関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="exceptions"></a>例外  
 `wcrtomb_s` 関数は、この関数の実行中に現行スレッドのどの関数も `setlocale` を呼び出さず、かつ `mbstate` が null である限り、マルチスレッド セーフです。  
  
## <a name="example"></a>例  
  
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
The corresponding wide character "Q" was converted to a the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`wcrtomb_s`|\<wchar.h>|  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)