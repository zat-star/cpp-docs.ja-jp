---
title: mbrlen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords: mbrlen
dev_langs: C++
helpviewer_keywords: mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 58f94a79bb5304ed1ebfe9b7c2241b28497c8c4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mbrlen"></a>mbrlen
現在のロケールのマルチバイト文字を完成させるのに必要なバイト数を決定します。マルチバイト文字の途中から再開することが可能です。  
  
## <a name="syntax"></a>構文  
  
```  
size_t mbrlen(  
   const char * str,  
   size_t count,  
   mbstate_t * mbstate  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 マルチバイト文字列内の検査対象となる次のバイトへのポインター。  
  
 `count`  
 検査対象の最大バイト数。  
  
 `mbstate`  
 `str` の最初のバイトの現在のシフト状態へのポインター。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
 0  
 次の `count` 以下のバイトで、ワイド null 文字を表すマルチバイト文字が完成します。  
  
 1 ～ `count` (両端を含む)  
 次の `count` 以下のバイトで、有効なマルチバイト文字が完成します。 返される値は、マルチバイト文字を完成するのに必要なバイト数です。  
  
 (size_t)(-2)  
 次の `count` バイトは、不完全ながら有効になり得るマルチバイト文字に寄与し、すべての `count` バイトが処理されています。  
  
 (size_t)(-1)  
 エンコーディング エラーが発生しました。 次の `count` 以下のバイト数は、完全かつ有効なマルチバイト文字に寄与しません。 この場合、 `errno` が EILSEQ に設定され、`mbstate` の変換状態は指定されていません。  
  
## <a name="remarks"></a>コメント  
 `mbrlen` 関数は、`count` がポイントするバイトで始まる最大 `str` バイトを検査して、シフト シーケンスを含む次のマルチバイト文字を完成させるのに必要なバイト数を判別します。 これは呼び出し `mbrtowc(NULL, str, count, &mbstate)` に相当します。ここで、`mbstate` はユーザー指定の `mbstate_t` オブジェクト、またはライブラリが指定する静的な内部オブジェクトのいずれかです。  
  
 `mbrlen` 関数は、`mbstate` パラメーターの不完全なマルチバイト文字のシフト状態を格納して使用します。 これにより、`mbrlen` が最大で `count` バイト確認する際、必要に応じてマルチバイト文字の途中から再開できるようになります。 `mbstate` が null ポインターの場合、`mbrlen` は内部の静的な `mbstate_t` オブジェクトを使用してシフト状態を格納します。 内部 `mbstate_t` オブジェクトはスレッド セーフではないため、常に独自の `mbstate` パラメーターを割り当てて渡すことをお勧めします。  
  
 `mbrlen` 関数は、再開できるかどうかの点で [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md) と異なります。 同じ関数または再開可能な他の関数の後続の呼び出しのために、シフト状態が `mbstate` に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、`wcsrlen` の代わりに `wcslen` の後続の呼び出しが使用されている場合、アプリケーションは `wcsrtombs` の代わりに `wcstombs.` を使用する必要があります。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|該当なし|該当なし|`mbrlen`|該当なし|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`mbrlen`|\<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 この例は、マルチバイト文字の解釈が現在のコード ページによってどのように異なるかを示し、`mbrlen` の再開機能の例を示します。  
  
```C  
// crt_mbrlen.c  
// Compile by using: cl crt_mbrlen.c  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <locale.h>  
#include <wchar.h>  
  
size_t Example(const char * pStr)  
{  
    size_t      charLen = 0;  
    size_t      charCount = 0;  
    mbstate_t   mbState = {0};  
  
    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&  
            charLen != (size_t)-1)  
    {  
        if (charLen != (size_t)-2) // if complete mbcs char,  
        {  
            charCount++;  
        }  
    }   
    return (charCount);  
}   
  
int main( void )  
{  
    int         cp;  
    size_t      charCount = 0;  
    const char  *pSample =   
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";  
  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
  
    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale  
    _setmbcp(932); // and Japanese multibyte code page  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
}  
```  
  
```Output  
  
Code page: 0  
é╨éτé¬é╚: Shift-jis hiragana.  
Character count: 29  
  
Code page: 932  
????: Shift-jis hiragana.  
Character count: 25  
  
```  
  
## <a name="see-also"></a>参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)