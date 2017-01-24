---
title: "abs、labs、llabs、_abs64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "abs"
  - "_abs64"
  - "labs"
  - "llabs"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "stdlib/_abs64"
  - "math/abs"
  - "_abs64"
  - "abs"
  - "labs"
  - "math/labs"
  - "llabs"
  - "math/llabs"
  - "cmath/abs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "絶対値"
  - "abs 関数"
  - "abs64 関数"
  - "_abs64 関数"
  - "計算 (絶対値を)"
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# abs、labs、llabs、_abs64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数の絶対値を計算します。  
  
## 構文  
  
```  
int abs(   
   int n   
);  
long abs(   
   long n   
);   // C++ only  
long long abs(   
   long long n   
);   // C++ only  
double abs(   
   double n   
);   // C++ only  
long double abs(  
   long double n  
);   // C++ only  
float abs(  
   float n   
);   // C++ only  
long labs(  
   long n   
);  
long long llabs(  
   long long n   
);  
__int64 _abs64(   
   __int64 n   
);  
```  
  
#### パラメーター  
 `n`  
 数値を指定します。  
  
## 戻り値  
 `abs`, 、`labs`, 、`llabs` と `_abs64` 関数がパラメーターの絶対値を返す `n`します。 エラーの戻り値はありません。  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`abs`, `long`、`long long`、`float`、および `double` の値を受け取って返す `long double` のオーバーロードを呼び出すことができます。 これらのオーバー ロードは、\< cmath \> ヘッダーで定義されます。 C プログラムでは、`abs` は常に整数を受け取り、整数を返します。  
  
 **Microsoft 固有の仕様**  
  
 任意の整数型を使用して表すことができる負の整数の範囲は、正の整数のタイプを使用して表すことができる範囲よりも大きいために、これらの関数を変換できない引数を指定することです。 引数の絶対値を戻り値の型で表すことができない場合、`abs` 関数は引数の値を変更せずに返します。 具体的には、`abs(INT_MIN)` は `INT_MIN` を返し、`labs(LONG_MIN)` は `LONG_MIN` を返します。また `llabs(LLONG_MIN)` は `LLONG_MIN` を返し、`_abs64(_I64_MIN)` は `_I64_MIN` を返します。 このため、`abs` 関数を使用して正の値を保証することはできません。  
  
 **END Microsoft 固有の仕様**  
  
## 必要条件  
  
|ルーチン|必須の C ヘッダー|必要な C\+\+ ヘッダー|  
|----------|----------------|--------------------|  
|`abs`、`labs`、`llabs`|\< math.h \> または \< stdlib.h \>|\< cmath \>、\< cstdlib \> \< stdlib.h \> または \< math.h \>|  
|`_abs64`|\<stdlib.h\>|\< cstdlib \> または \< stdlib.h \>|  
  
 オーバー ロードされたバージョンを使用して `abs` C\+\+ では、\< cmath \> ヘッダーを含める必要があります。  
  
## 使用例  
 次のプログラムでは、複数の数値の絶対値を計算して表示します。  
  
```c  
// crt_abs.c  
// Build: cl /W3 /TC crt_abs.c  
// This program demonstrates the use of the abs function  
// by computing and displaying the absolute values of  
// several numbers.  
  
#include <stdio.h>  
#include <math.h>  
#include <stdlib.h>  
#include <limits.h>  
  
int main( void )  
{  
    int ix = -4;  
    long lx = -41567L;  
    long long llx = -9876543210LL;  
    __int64 wx = -1;  
  
    // absolute 32 bit integer value  
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));  
  
    // absolute long integer value  
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));  
  
    // absolute long long integer value  
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));  
  
    // absolute 64 bit integer value  
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,   
        _abs64(wx));  
  
    // Integer error cases:  
    printf_s("Microsoft implementation-specific results:\n");  
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));  
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));  
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));  
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));  
}  
```  
  
```Output  
-4 の絶対値は 4-41567 の絶対値は 41567-9876543210 の絶対値は 9876543210 0 xffffffffffffffff の絶対値は 0x0000000000000001 Microsoft の実装に固有の結果: abs (int_min) を返します-2147483648 labs (long_min)-2147483648 を返します。 llabs (llong_min)-9223372036854775808 を返します。 _abs64 (_i64_min) を返します。 は 0x8000000000000000。  
  
```  
  
## 同等の .NET Framework 関数  
 [System::Math::Abs](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_cabs](../Topic/_cabs.md)   
 [fabs、fabsf、fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [imaxabs](../Topic/imaxabs.md)