---
title: _set_output_format | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_output_format
apilocation:
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- set_output_format
- _set_output_format
dev_langs:
- C++
helpviewer_keywords:
- _TWO_DIGIT_EXPONENT constant
- output formatting
- TWO_DIGIT_EXPONENT constant
- _set_output_format function
- set_output_format function
ms.assetid: 1cb48df8-44b4-4400-bd27-287831d6b3ff
caps.latest.revision: 17
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
ms.translationtype: Human Translation
ms.sourcegitcommit: aadbf7d2c6fece48ab29c1b818995464a790c38b
ms.openlocfilehash: 602f4460af0e08e6515fb4559bec2d49bbc56e75
ms.contentlocale: ja-jp
ms.lasthandoff: 03/07/2017

---
# <a name="setoutputformat"></a>_set_output_format
書式付き I/O 関数で使用する出力形式をカスタマイズします。  
  
> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降、CRT で使用できません。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned int _set_output_format(  
   unsigned int format  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `format`  
 使用する書式を表す値。  
  
## <a name="return-value"></a>戻り値  
 以前の出力形式。  
  
## <a name="remarks"></a>コメント  
 `_set_output_format` は、[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) などの書式付き I/O 関数の出力を構成する場合に使用します。 現時点では、この関数で変更できる書式設定規則は、浮動小数点数の出力の指数部に表示される桁数のみです。  
  
 既定では、 `printf_s`、 `wprintf_s`、およびそれに関連する Visual C++ 標準ライブラリ関数によって出力される浮動小数点数の指数部は、指数部の値を表すために&3; 桁が必要でない場合でも、3 桁で出力されます。 値が&3; 桁になるように&0; が埋め込まれます。 `_set_output_format` を使用すると、指数部の大きさによって&3; 桁目が必要になる場合を除いて、浮動小数点数の指数部が&2; 桁のみで出力されるように動作を変更できます。  
  
 2 桁の指数部を有効にするには、次の例に示されているとおり、パラメーター `_TWO_DIGIT_EXPONENT`を指定してこの関数を呼び出します。 2 桁の指数部を無効にするには、引数 0 を指定してこの関数を呼び出します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_set_output_format`|\<stdio.h>|  
  
 互換性について詳しくは、概要の「[互換性](../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```C  
// crt_set_output_format.c  
#include <stdio.h>  
  
void printvalues(double x, double y)  
{  
   printf_s("%11.4e %11.4e\n", x, y);  
   printf_s("%11.4E %11.4E\n", x, y);  
   printf_s("%11.4g %11.4g\n", x, y);  
   printf_s("%11.4G %11.4G\n", x, y);  
}  
  
int main()  
{  
   double x = 1.211E-5;  
   double y = 2.3056E-112;  
   unsigned int old_exponent_format;  
  
   // Use the default format  
   printvalues(x, y);  
  
   // Enable two-digit exponent format  
   old_exponent_format = _set_output_format(_TWO_DIGIT_EXPONENT);  
  
   printvalues(x, y);  
  
   // Disable two-digit exponent format  
   _set_output_format( old_exponent_format );  
  
   printvalues(x, y);  
}  
```  
  
```Output  
1.2110e-005 2.3056e-112  
1.2110E-005 2.3056E-112  
 1.211e-005  2.306e-112  
 1.211E-005  2.306E-112  
 1.2110e-05 2.3056e-112  
 1.2110E-05 2.3056E-112  
  1.211e-05  2.306e-112  
  1.211E-05  2.306E-112  
1.2110e-005 2.3056e-112  
1.2110E-005 2.3056E-112  
 1.211e-005  2.306e-112  
 1.211E-005  2.306E-112  
```  
  
## <a name="see-also"></a>関連項目  
 [printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [_get_output_format](../c-runtime-library/get-output-format.md)
