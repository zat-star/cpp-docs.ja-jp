---
title: mbrtowc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- mbrtowc
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
- mbrtowc
dev_langs:
- C++
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f3446132532fbf212294c0176b697359572b235
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="mbrtowc"></a>mbrtowc
現在のロケールのマルチバイト文字を、それに対応するワイド文字に変換します。マルチバイト文字の途中から再開することが可能です。  
  
## <a name="syntax"></a>構文  
  
```  
size_t mbrtowc(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count,  
   mbstate_t *mbstate  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `wchar`  
 変換されたワイド文字の文字列を受け取るワイド文字のアドレス (型 `wchar_t`)。 ワイド文字を返す必要がない場合、この値は null ポインターを指定できます。  
  
 `mbchar`  
 バイト シーケンスのアドレス (マルチバイト文字)。  
  
 `count`  
 チェックするバイト数。  
  
 `mbstate`  
 変換状態のオブジェクトへのポインター。 この値が null ポインターの場合、関数は静的な内部変換状態オブジェクトを使用します。 内部 `mbstate_t` オブジェクトはスレッド セーフではないため、常に独自の `mbstate` 引数を渡すことをお勧めします。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
 0  
 次の `count` 以下のバイトで null ワイド文字を表すマルチバイト文字が完成します。これは、`wchar` がnull ポインターでない場合に `wchar` に格納されます。  
  
 1 ～ `count` (両端を含む)  
 次の `count` 以下のバイトで、有効なマルチバイト文字が完成します。 返される値は、マルチバイト文字を完成するのに必要なバイト数です。 `wchar` が null ポインターでない場合に、同等のワイド文字が `wchar` に格納されます。  
  
 (size_t)(-1)  
 エンコーディング エラーが発生しました。 次の `count` 以下のバイト数は、完全かつ有効なマルチバイト文字に寄与しません。 この場合、`errno` が EILSEQ に設定され、`mbstate` の変換のシフト状態は指定されていません。  
  
 (size_t)(-2)  
 次の `count` バイトは、不完全ながら有効になり得るマルチバイト文字に寄与し、すべての `count` バイトが処理されています。 `wchar` に値は格納されませんが、関数を再開するために `mbstate` が更新されます。  
  
## <a name="remarks"></a>コメント  
 `mbchar` が null ポインターの場合、関数は呼び出しに相当します。  
  
 `mbrtowc(NULL, "", 1, &mbstate)`  
  
 この場合は、引数 `wchar` と `count` の値は無視されます。  
  
 `mbchar` が null ポインターでない場合、関数は `count` から `mbchar` バイトを調べて、次のマルチバイト文字を完成させるのに必要なバイト数を判別します。 次の文字が有効な場合は、対応するマルチバイト文字が `wchar` に格納されます (null ポインターではない場合)。 文字が対応するワイド null 文字の場合、`mbstate` の結果の状態は初期の変換状態になります。  
  
 `mbrtowc` 関数は、再開できるかどうかの点で [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md) と異なります。 同じ関数または再開可能な他の関数の後続の呼び出しのために、変換状態が `mbstate` に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、`wcsrlen` の代わりに `wcslen` の後続の呼び出しが使用されている場合、アプリケーションは `wcsrtombs` の代わりに `wcstombs` を使用する必要があります。  
  
## <a name="example"></a>例  
 マルチバイト文字を対応するワイド文字に変換します。  
  
```  
// crt_mbrtowc.cpp  
  
#include <stdio.h>  
#include <mbctype.h>  
#include <string.h>  
#include <locale.h>  
#include <wchar.h>  
  
#define BUF_SIZE 100  
  
int Sample(char* szIn, wchar_t* wcOut, int nMax)  
{  
    mbstate_t   state = {0}; // Initial state  
    size_t      nConvResult,   
                nmbLen = 0,  
                nwcLen = 0;  
    wchar_t*    wcCur = wcOut;  
    wchar_t*    wcEnd = wcCur + nMax;  
    const char* mbCur = szIn;  
    const char* mbEnd = mbCur + strlen(mbCur) + 1;  
    char*       szLocal;  
  
    // Sets all locale to French_Canada.1252  
    szLocal = setlocale(LC_ALL, "French_Canada.1252");  
    if (!szLocal)  
    {  
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");  
        return 1;  
    }  
  
    printf("Locale set to: \"%s\"\n", szLocal);  
  
    // Sets the code page associated current locale's code page  
    // from a previous call to setlocale.  
    if (_setmbcp(_MB_CP_SBCS) == -1)  
    {  
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");  
        return 1;  
    }  
  
    while ((mbCur < mbEnd) && (wcCur < wcEnd))  
    {  
        //  
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);  
        switch (nConvResult)  
        {  
            case 0:  
            {  // done  
                printf("Conversion succeeded!\nMultibyte String: ");  
                printf(szIn);  
                printf("\nWC String: ");  
                wprintf(wcOut);  
                printf("\n");  
                mbCur = mbEnd;  
                break;  
            }  
  
            case -1:  
            {  // encoding error  
                printf("The call to mbrtowc has detected an encoding error.\n");  
                mbCur = mbEnd;  
                break;  
            }  
  
            case -2:  
            {  // incomplete character  
                if   (!mbsinit(&state))  
                {  
                    printf("Currently in middle of mb conversion, state = %x\n", state);  
                    // state will contain data regarding lead byte of mb character  
                }  
  
                ++nmbLen;  
                ++mbCur;  
                break;  
            }  
  
            default:  
            {  
                if   (nConvResult > 2) // The multibyte should never be larger than 2  
                {  
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);  
                }  
  
                ++nmbLen;  
                ++nwcLen;  
                ++wcCur;  
                ++mbCur;  
            break;  
            }  
        }  
    }  
  
   return 0;  
}  
  
int main(int argc, char* argv[])  
{  
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";  
    wchar_t wcBuf[BUF_SIZE] = {L''};  
  
    return Sample(mbBuf, wcBuf, BUF_SIZE);  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Locale set to: "French_Canada.1252"  
Conversion succeeded!  
Multibyte String: AaBbCcÜïα∩≡xXyYzZ  
WC String: AaBbCcÜïα∩≡xXyYzZ  
```  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`mbrtowc`|\<wchar.h>|  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)