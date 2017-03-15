---
title: wcrtomb | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcrtomb
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
f1_keywords:
- wcrtomb
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 853295a50158caa92ed9370b6267e4e623f7d790
ms.lasthandoff: 02/24/2017

---
# <a name="wcrtomb"></a>wcrtomb
ワイド文字をマルチバイト文字の表現に変換します。 この関数のセキュリティが強化されたバージョンについては、「[wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 [出力] `mbchar`  
 結果として得られるマルチバイトに変換された文字。  
  
 [入力] `wchar`  
 変換するワイド文字。  
  
 [入力] `mbstate`  
 `mbstate_t` オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 変換されたマルチバイト文字を表すのに必要なバイト数を返します。エラーが発生した場合は -1 を返します。  
  
## <a name="remarks"></a>コメント  
 `wcrtomb` 関数は、`mbstate` に含まれる指定された変換の状態で始まるワイド文字を、`wchar` に含まれている値から、`mbchar` によって表されるアドレスに変換します。 戻り値は対応するマルチバイト文字を表すために必要なバイト数ですが、`MB_CUR_MAX` バイトより大きな値を返すことはありません。  
  
 `mbstate` が null の場合、`mbchar` の変換状態を含む内部 `mbstate_t` オブジェクトが使用されます。 文字シーケンス `wchar` に対応するマルチバイト文字の表現がない場合、-1 が返され、`errno` が `EILSEQ` に設定されます。  
  
 `wcrtomb` 関数は、再開できるかどうかの点で [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) と異なります。 同じ関数または再開可能な他の関数の後続の呼び出しのために、変換状態が `mbstate` に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは `wcsrlen` を使用し、`wcsnlen` は使用しないことがあります。これは、後続の呼び出しで `wcsrtombs` を使用しており、`wcstombs` は使用しない場合です。  
  
 C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="exceptions"></a>例外  
 `wcrtomb` 関数は、この関数の実行中に現行スレッドのどの関数も `setlocale` を呼び出さず、かつ `mbstate` が null である限り、マルチスレッド セーフです。  
  
## <a name="example"></a>例  
  
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
  
```Output  
The corresponding wide character "Q" was converted to the "Q" multibyte character.  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`wcrtomb`|\<wchar.h>|  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
