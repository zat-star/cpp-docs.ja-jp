---
title: "_atoi64、_atoi64_l、_wtoi64、_wtoi64_l |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _atoi64_l
- _wtoi64
- _atoi64
- _wtoi64_l
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
- _atoi64
- _tstoi64
- _ttoi64
- wtoi64
- _tstoi64_l
- atoi64
- _wtoi64_l
- _wtoi64
- wtoi64_l
- _atoi64_l
- atoi64_l
dev_langs:
- C++
helpviewer_keywords:
- tstoi64 function
- wtoi64 function
- atoi64_l function
- _ttoi64 function
- string conversion, to integers
- wtoi64_l function
- atoi64 function
- _tstoi64 function
- _atoi64_l function
- _wtoi64_l function
- ttoi64 function
- _wtoi64 function
- _atoi64 function
ms.assetid: 2c3e30fd-545d-4222-8364-0c5905df9526
caps.latest.revision: 24
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 749ce35fdb4ed530bf301539b13ba3cb0471b996
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="atoi64-atoi64l-wtoi64-wtoi64l"></a>_atoi64、_atoi64_l、_wtoi64、_wtoi64_l
文字列を 64 ビット整数に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
__int64 _atoi64(  
   const char *str   
);  
__int64 _wtoi64(  
   const wchar_t *str   
);  
__int64 _atoi64_l(  
   const char *str,  
   _locale_t locale  
);  
__int64 _wtoi64_l(  
   const wchar_t *str,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 変換対象の文字列。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 各関数は、入力文字を数字として解釈して生成される `__int64` 値を返します。 入力をその型の値に変換できない場合、`_atoi64` の戻り値は 0 になります。  
  
 より大きい正の整数値によるオーバーフローの場合、`_atoi64` は `I64_MAX` を返し、より大きい負の整数値によるオーバーフローの場合は `I64_MIN` を返します。  
  
 範囲外のすべての場合、`errno` は `ERANGE` に設定されます。 渡されたパラメーターが `NULL` である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
## <a name="remarks"></a>コメント  
 これらの関数は、文字列を 64 ビット整数値に変換します。  
  
 入力文字列は、指定された型の数値として解釈できる文字シーケンスです。 関数は、数値の一部として認識できない文字に最初に遭遇した時点で入力文字列の読み取りを停止します。 この文字は、文字列を終了する null 文字 ('\0' または L'\0') である場合があります。  
  
 `str` の `_atoi64` 引数には、次の形式があります。  
  
```  
[whitespace] [sign] [digits]]  
```  
  
 A`whitespace`は無視されますスペースまたはタブ文字で構成されています。`sign`はプラス (+) またはマイナス記号 (-) です。 と`digits`は 1 つ以上の数字です。  
  
 `_wtoi64` は、ワイド文字列をパラメーターとして受け取る点を除いて `_atoi64` と同じです。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tstoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
|`_ttoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|--------------|---------------------|  
|`_atoi64`, `_atoi64_l`|\<stdlib.h>|  
|`_wtoi64`, `_wtoi64_l`|\<stdlib.h> または \<wchar.h>|  
  
## <a name="example"></a>例  
 このプログラムは、`_atoi64` 関数を使用して、文字列として格納されている数字を数値に変換する方法を示します。  
  
```  
// crt_atoi64.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the _atoi64 functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    __int64 value = 0;  
  
    // An example of the _atoi64 function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
```Output  
Function: _atoi64( "  -2309 " ) = -2309  
Function: _atoi64( "314127.64" ) = 314127  
Function: _atoi64( "3336402735171707160320" ) = -1  
Overflow condition occurred.  
```  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_atodbl、_atodbl_l、_atoldbl、_atoldbl_l、_atoflt、_atoflt_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)
