---
title: _ecvt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _ecvt
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
f1_keywords: _ecvt
dev_langs: C++
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 237924bce3bb4b659e72cec060738035d91c7cbc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ecvt"></a>_ecvt
`double` の値を文字列に変換します。 この関数のセキュリティが強化されたバージョンについては、「[_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *_ecvt(   
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
 格納する桁数。  
  
 `dec`  
 格納された小数点位置。  
  
 `sign`  
 変換後の数値の符号。  
  
## <a name="return-value"></a>戻り値  
 `_ecvt` は数字の文字列へのポインターを返します。エラーが発生した場合は NULL です。  
  
## <a name="remarks"></a>コメント  
 `_ecvt` 関数は、浮動小数点数の値を文字列に変換します。 `value` パラメーターは変換する浮動小数点数です。 この関数は、`value` の最大 `count` 桁を文字列として格納し、null 文字 ("\0") を追加します。 `value` の桁数が `count` を超える場合、下位の桁は丸められます。 `count` 桁より少ない場合は、文字列が 0 で埋められます。  
  
 `_ecvt` によって返される桁の総数は、`_CVTBUFSIZE` 以下である必要があります。  
  
 文字列には数字だけが格納されます。 `value` の小数点位置と符号は、呼び出しの後で `dec` と `sign` から取得できます。 `dec` パラメーターは、文字列の先頭に対する小数点位置を示す整数値をポイントします。 0 または負の整数値は、最初の桁の左側に小数点があることを示します。 `sign` パラメーターは、変換後の数値の符号を示す整数をポイントします。 整数値が 0 の場合、数値は正の値です。 それ以外の場合、数値は負の値です。  
  
 `_ecvt` と `_fcvt` の違いは、`count` パラメーターの解釈です。 `_ecvt` が `count` を出力文字列全体の桁数として解釈するのに対し、`_fcvt` は `count` を小数点より後の桁数と解釈します。  
  
 `_ecvt` と `_fcvt` は、静的に割り当てられた共通のバッファーを使って変換を行います。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。  
  
 この関数は、パラメーターを検証します。 `dec` または `sign` が NULL の場合、または `count` が 0 の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、NULL が返されます。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_ecvt`|\<stdlib.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0  
```  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)