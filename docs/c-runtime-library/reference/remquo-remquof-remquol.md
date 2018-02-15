---
title: "remquo、remquof、remquol | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- remquof
- remquo
- remquol
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- remquof
- remquol
- remquo
dev_langs:
- C++
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: deb68c536acab80077870bbc0b16ef171edb1d87
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="remquo-remquof-remquol"></a>remquo、remquof、remquol
2 個の整数値の剰余を計算し、パラメーターに指定された位置に、整数値を符号と商の近似値と共に格納します。  
  
## <a name="syntax"></a>構文  
  
```  
double remquo(   
   double numer,  
   double denom,  
   int* quo  
);  
float remquo(   
   float numer,  
   float denom,  
   int* quo  
); /* C++ only */  
long double remquo(   
   long double numer,  
   long double denom,  
   int* quo  
); /* C++ only */  
float remquof(   
   float numer,  
   float denom,  
   int* quo  
);  
long double remquol(   
   long double numer,  
   long double denom,  
   int* quo  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `numer`  
 分子。  
  
 `denom`  
 分母。  
  
 `quo`  
 符号と商の近似値を持つ値を格納する整数へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `remquo` は、`x` / `y` の浮動小数点の剰余を返します。 `y` の値が 0.0 の場合、`remquo` は簡易な NaN を返します。 `printf` ファミリによる簡易な NaN の表現については、「[printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `remquo` 関数は、`x` = `i` `*` `y` + `f` となる `x` / `y` の剰余 `f` を浮動小数点型で計算します。`i` は整数であり、`f` の符号は `x` と同じであり、`f` の絶対値は `y` の絶対値未満です。  
  
 C++ ではオーバーロードが可能であるため、`remquo` または `float` の値を受け取って返す `long double` のオーバーロードを呼び出すことができます。 C プログラムでは、`remquo` は常に 2 個の double を受け取って、1 個の double を返します。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`remquo`、`remquof`、`remquol`|\<math.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```C  
// crt_remquo.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
   int quo = 0;  
  
   z = remquo(w, x, &quo);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
   printf("Approximate signed quotient is %d\n", quo);  
}  
```  
  
```Output  
The remainder of -10.00 / 3.00 is -1.000000  
Approximate signed quotient is -3  
```  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ldiv、lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod、fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remainder、remainderf、remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)