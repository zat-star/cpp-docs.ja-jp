---
title: "_fcvt | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fcvt
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
- _fcvt
dev_langs:
- C++
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
caps.latest.revision: 24
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
ms.openlocfilehash: 9f191d64115bca85502d8fd3fbe0525c0e2be65c
ms.lasthandoff: 02/24/2017

---
# <a name="fcvt"></a>_fcvt
浮動小数点数を文字列に変換します。 この関数のセキュリティが強化されたバージョンについては、「[_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
char *_fcvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value`  
 変換される数値。  
  
 `count`  
 小数点以下の桁数。  
  
 `dec`  
 格納された小数点位置を指すポインター。  
  
 `sign`  
 格納された符号インジケーターを指すポインター。  
  
## <a name="return-value"></a>戻り値  
 `_fcvt` は、数字の文字列エラーを指すポインターを返します。エラーの場合は NULL を返します。  
  
## <a name="remarks"></a>コメント  
 `_fcvt` 関数は、浮動小数点数の値を null で終わる文字列に変換します。 `value` パラメーターは変換する浮動小数点数です。 `_fcvt` は、`value` の桁数を文字列として格納し、null 文字 ("\0") を追加します。 `count` パラメーターは、小数点より後の格納する桁数を指定します。 余分な桁は、`count` 桁まで丸められます。 この桁数が `count` の有効桁数より少ない場合は、文字列に&0; が埋め込まれます。  
  
 `_fcvt` によって返される桁の総数は、`_CVTBUFSIZE` 以下である必要があります。  
  
 文字列には数字だけが格納されます。 `value` の小数点位置と符号は、呼び出しの後で `dec` と sign から取得できます。 `dec` パラメーターは、整数値を指します。この整数値は、小数点が文字列の先頭から何文字目にあるのかを示します。 0 または負の整数値は、小数点が文字列の先頭より左にあることを示します。 `sign` パラメーターは、`value` の符号を示す整数を指します。 `value` が正の場合、整数は 0 に設定され、`value` が負の場合は負の値に設定されます。  
  
 `_ecvt` と `_fcvt` の違いは、`count` パラメーターの解釈にあります。 `_ecvt` が `count` を出力文字列全体の桁数として解釈するのに対し、`_fcvt` は `count` を小数点より後の桁数と解釈します。  
  
 `_ecvt` と `_fcvt` は、静的に割り当てられた共通のバッファーを使って変換を行います。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。  
  
 この関数は、パラメーターを検証します。 `dec` または `sign` が NULL の場合、または `count` が 0 の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、NULL が返されます。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_fcvt`|\<stdlib.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_fcvt.c  
// compile with: /W3  
// This program converts the constant  
// 3.1415926535 to a string and sets the pointer  
// buffer to point to that string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  decimal, sign;  
   char *buffer;  
   double source = 3.1415926535;  
  
   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996  
   // Note: _fcvt is deprecated; consider using _fcvt_s instead  
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",  
            source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)
