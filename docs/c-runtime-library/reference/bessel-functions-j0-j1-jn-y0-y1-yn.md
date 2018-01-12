---
title: "Bessel 系関数: _j0、_j1、_jn、_y0、_y1、_yn | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
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
- c.bessel
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
dev_langs: C++
helpviewer_keywords:
- Bessel functions
- _j0 function
- _j1 function
- _jn function
- _y0 function
- _y1 function
- _yn function
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0d2b866c847055a37e4415b020b3e7e02fdaa5f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bessel-functions-j0-j1-jn-y0-y1-yn"></a>Bessel 系関数: _j0、_j1、_jn、_y0、_y1、_yn
0、1、または n の順序の、最初または 2 番目の種類の Bessel 関数を計算します。 Bessel 系関数は電磁波理論の数学でよく使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
double _j0(   
   double x   
);  
double _j1(   
   double x   
);  
double _jn(   
   int n,  
   double x   
);  
double _y0(   
   double x   
);  
double _y1(   
   double x   
);  
double _yn(   
   int n,  
   double x   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 浮動小数点値。  
  
 `n`  
 Bessel 系関数の整数順序。  
  
## <a name="return-value"></a>戻り値  
 これらのルーチンはそれぞれ、 `x`の Bessel 関数を返します。 `x` 、 `_y0`、または `_y1`関数で `_yn` が負の場合、ルーチンは `errno` を `EDOM`に設定し、 `_DOMAIN` エラー メッセージを `stderr`に出力し、 `_HUGE_VAL`を返します。 `_matherr`を使用することにより、エラー処理を変更することができます。  
  
## <a name="remarks"></a>コメント  
 `_j0`ルーチン、 `_j1`ルーチン、 `_jn` ルーチンは、最初の種類の Bessel 関数を返します。順序はそれぞれ、0、1、n です。  
  
|入力|SEH 例外|Matherr 例外|  
|-----------|-------------------|-----------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
  
 `_y0`ルーチン、 `_y1`ルーチン、 `_yn` ルーチンは、2 番目の種類の Bessel 関数を返します。順序はそれぞれ、0、1、n です。  
  
|入力|SEH 例外|Matherr 例外|  
|-----------|-------------------|-----------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
|± 0|`ZERODIVIDE`|`_SING`|  
|&#124;x&#124;<0.0|`INVALID`|`_DOMAIN`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn`|\<cmath> (C++), \<math.h> (C, C++)|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_bessel1.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.387;  
   int n = 3, c;  
  
   printf( "Bessel functions for x = %f:\n", x );  
   printf( " Kind   Order  Function     Result\n\n" );  
   printf( " First  0      _j0( x )     %f\n", _j0( x ) );  
   printf( " First  1      _j1( x )     %f\n", _j1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );  
   printf( " Second 0      _y0( x )     %f\n", _y0( x ) );  
   printf( " Second 1      _y1( x )     %f\n", _y1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );  
}  
```  
  
```Output  
Bessel functions for x = 2.387000:  
 Kind   Order  Function     Result  
  
 First  0      _j0( x )     0.009288  
 First  1      _j1( x )     0.522941  
 First  2      _jn( 2, x )  0.428870  
 First  3      _jn( 3, x )  0.195734  
 First  4      _jn( 4, x )  0.063131  
 Second 0      _y0( x )     0.511681  
 Second 1      _y1( x )     0.094374  
 Second 2      _yn( 2, x )  -0.432608  
 Second 3      _yn( 3, x )  -0.819314  
 Second 4      _yn( 4, x )  -1.626833  
```  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_matherr](../../c-runtime-library/reference/matherr.md)