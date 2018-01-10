---
title: wcsrtombs_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcsrtombs_s
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
f1_keywords: wcsrtombs_s
dev_langs: C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 025acdf18d0e5322ef43de800e3577233a93cb86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="wcsrtombss"></a>wcsrtombs_s
ワイド文字の文字列をマルチバイト文字の文字列表現に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおりセキュリティが強化されたバージョンの [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) です。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pReturnValue`  
 変換された文字数。  
  
 [出力] `mbstr`  
 結果として変換されたマルチバイト文字の文字列のバッファーのアドレス。  
  
 [出力] `sizeInBytes`  
 `mbstr` バッファーのサイズ (バイト数)。  
  
 [入力] `wcstr`  
 変換するワイド文字の文字列を指します。  
  
 [入力] `count`  
 `mbstr`バッファーに格納される最大バイト数、または [_TRUNCATE](../../c-runtime-library/truncate.md)。  
  
 [入力] `mbstate`  
 `mbstate_t` 変換状態オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
|エラー条件|戻り値および `errno`|  
|---------------------|------------------------------|  
|`mbstr` が `NULL` で `sizeInBytes` > 0|`EINVAL`|  
|`wcstr` は `NULL` です|`EINVAL`|  
|コピー先のバッファーが小さすぎて変換後の文字列を含めることができません (`count` が `_TRUNCATE` の場合を除きます。下記の「解説」を参照してください)|`ERANGE`|  
  
 これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行の続行が許可された場合、関数はエラー コードを返し、表に示すように `errno` を設定します。  
  
## <a name="remarks"></a>コメント  
 `wcsrtombs_s` 関数は、`wcstr` が指すワイド文字の文字列を、`mbstate` に含まれる変換状態を使用して、`mbstr` が指すバッファーに格納されるマルチバイト文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。  
  
-   ワイド文字の null が検出されました。  
  
-   変換できないワイド文字が検出されました。  
  
-   `mbstr` バッファーに格納されているバイト数が `count` と同じです。  
  
 変換先の文字列は、エラーの場合を含め、常に null で終わります。  
  
 `count` が特殊値 [_TRUNCATE](../../c-runtime-library/truncate.md) の場合、`wcsrtombs_s` は null 終端文字用の空きを残して、コピー先のバッファーに収まる限りの文字列を変換します。  
  
 `wcsrtombs_s` は、元の文字列を正常に変換すると、null 終端文字を含む変換後の文字列のサイズ (バイト数) を `*pReturnValue` に書き込みます (`pReturnValue` が `NULL`でない場合に限ります)。 これは、`mbstr` 引数が `NULL` である場合でも発生し、必要なバッファー サイズを決定する方法を提供します。 `mbstr` が `NULL` の場合は、`count` は無視されることに注意してください。  
  
 マルチバイト文字に変換できないワイド文字が検出された場合、`wcsrtombs_s` は `*pReturnValue` に -1 を入れ、コピー先バッファーを空文字列に設定し、`errno` を `EILSEQ` に設定して、`EILSEQ` を返します。  
  
 `wcstr` および `mbstr` が指すシーケンスが重なり合う場合、`wcsrtombs_s` の動作は未定義です。 `wcsrtombs_s` は、現在のロケールの LC_TYPE カテゴリの影響を受けます。  
  
> [!IMPORTANT]
>  `wcstr` と `mbstr` が重なり合わず、変換するワイド文字の数が `count` に適切に反映されていることを確認します。  
  
 `wcsrtombs_s` 関数は、再開できるかどうかの点で [wcstombs_s、_wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md) と異なります。 同じ関数または再開可能な他の関数の後続の呼び出しのために、変換状態が `mbstate` に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは `wcsrlen` を使用し、`wcslen` は使用しないことがあります。これは、後続の呼び出しで `wcsrtombs_s` を使用しており、`wcstombs_s.` は使用しない場合です。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="exceptions"></a>例外  
 `wcsrtombs_s` 関数は、この関数の実行中に現行スレッドのどの関数も `setlocale` を呼び出さず、かつ `mbstate` が null である限り、マルチスレッド セーフです。  
  
## <a name="example"></a>例  
  
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
  
```Output  
The string was successfully converted.  
```  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`wcsrtombs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)