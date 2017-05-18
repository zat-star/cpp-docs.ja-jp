---
title: wcsrtombs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcsrtombs
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
- wcsrtombs
dev_langs:
- C++
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6dfe7e2293f9544b64a0dfd7dfaa1889e65a64dc
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="wcsrtombs"></a>wcsrtombs
ワイド文字の文字列をマルチバイト文字の文字列形式に変換します。 この関数のセキュリティが強化されたバージョンについては、「[wcsrtombs_s](../../c-runtime-library/reference/wcsrtombs-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 [出力] `mbstr`  
 結果として変換されたマルチバイト文字のアドレスの場所。  
  
 [入力] `wcstr`  
 変換されるワイド文字の文字列の場所を間接的に指します。  
  
 [入力] `count`  
 変換される文字数。  
  
 [入力] `mbstate`  
 `mbstate_t` 変換状態オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 正常に変換されたバイト数を返します (null で終了する null バイトがあっても含まれません)。それ以外の場合は、エラーが発生した場合に -1 を返します。  
  
## <a name="remarks"></a>コメント  
 `wcsrtombs` 関数は、`mbstate` に含まれる指定された変換の状態で始まるワイド文字の文字列を、`wcstr` で間接的に指されている値から `mbstr` のアドレスに変換します。 null で終了するワイド文字が発生した後、または対応しない文字が発生するか、次の文字が `count` に含まれる制限を超えるまで、各文字の変換が継続されます。 `wcsrtombs` は、`count` の発生前または発生時にワイド文字の null 文字 (L'\0') を検出すると、それを 8 ビットの 0 に変換して停止します。  
  
 このため、`mbstr` のマルチバイト文字の文字列が null 終了になるのは、`wcsrtombs` が変換中にワイド文字の null 文字を検出した場合だけです。 `wcstr` および `mbstr` が指すシーケンスが重なり合う場合、`wcsrtombs` の動作は未定義です。 `wcsrtombs` は、現在のロケールの LC_TYPE カテゴリの影響を受けます。  
  
 `wcsrtombs` 関数は、再開できるかどうかの点で [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) と異なります。 同じ関数または再開可能な他の関数の後続の呼び出しのために、変換状態が `mbstate` に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、アプリケーションは `wcsrlen` を使用し、`wcsnlen` は使用しないことがあります。これは、後続の呼び出しで `wcsrtombs` を使用しており、`wcstombs` は使用しない場合です。  
  
 `mbstr` 引数が `NULL` の場合、`wcsrtombs` は必要な対象文字列のサイズ (バイト数) を返します。 `mbstate` が null の場合、内部の `mbstate_t` 変換状態が使用されます。 文字シーケンス `wchar` に対応するマルチバイト文字の表現がない場合、-1 が返され、`errno` が `EILSEQ` に設定されます。  
  
 C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="exceptions"></a>例外  
 `wcsrtombs` 関数は、この関数の実行中に現行スレッドのどの関数も `setlocale` を呼び出さず、かつ `mbstate` が null でない限り、マルチスレッド セーフです。  
  
## <a name="example"></a>例  
  
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
  
```Output  
The string was successfuly converted.  
```  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`wcsrtombs`|\<wchar.h>|  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
