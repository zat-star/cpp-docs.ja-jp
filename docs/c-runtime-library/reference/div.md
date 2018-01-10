---
title: div | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: div
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords: div
dev_langs: C++
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a942c3414fa7801912de59ec41fd6477d7c19f2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="div"></a>div
2 つの整数値の商と剰余を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### <a name="parameters"></a>パラメーター  
 `numer`  
 分子。  
  
 `denom`  
 分母。  
  
## <a name="return-value"></a>戻り値  
 `div` 型の引数を使用して呼び出された `int` は、商と剰余で構成される `div_t` 型の構造を返します。 `long` 型の引数を持つオーバーロードの戻り値は `ldiv_t` です。 `div_t` および `ldiv_t` はともに STDLIB.H で定義されます。  
  
## <a name="remarks"></a>コメント  
 `div` 関数は `numer` を `denom` で割り、商と剰余を計算します。 [div_t](../../c-runtime-library/standard-types.md) 構造体には、商 `int quot`、および剰余 `int rem` が含まれます。 商の符号は、数学的な商の符号と同じです。 この絶対値が最も大きい整数であり、商の絶対値よりも小さくなります。 分母が 0 の場合、プログラムはエラー メッセージにより終了します。  
  
 `long` 型または `long long` 型の引数を使用するオーバーロードは、C++ コードにのみ使用できます。 戻り値の型 [ldiv_t](../../c-runtime-library/standard-types.md) には、メンバー `long quot` と `long rem` が含まれ、戻り値の型 [lldiv_t](../../c-runtime-library/standard-types.md) には `div_t` のメンバーと同じ意味を持つメンバー `long long quot` と `long long rem` が含まれます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`div`|\<stdlib.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
```Output  
x is 876, y is 13  
The quotient is 67, and the remainder is 5  
```  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ldiv、lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)