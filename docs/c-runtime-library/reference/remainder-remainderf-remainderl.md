---
title: "remainder、remainderf、remainderl | Microsoft Docs"
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
  - "remainderl"
  - "remainder"
  - "remainderf"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "remainderf"
  - "remainder"
  - "remainderl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remainderf"
  - "remainderl"
  - "remainder"
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remainder、remainderf、remainderl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

最も近い整数値に丸められる 2 個の浮動小数点値の商の剰余を計算します。  
  
## 構文  
  
```  
double remainder(   
   double numer,  
   double denom  
);  
float remainder(   
   float numer,  
   float denom  
); /* C++ only */  
long double remainder(   
   long double numer,  
   long double denom  
); /* C++ only */  
float remainderf(   
   float numer,  
   float denom  
);  
long double remainderl(   
   long double numer,  
   long double denom  
);  
  
```  
  
#### パラメーター  
 `numer`  
 分子。  
  
 `denom`  
 分母。  
  
## 戻り値  
 `x` \/ `y`浮動小数点の剰余。  `y` の値が 0.0 の場合、`remainder` は簡易な NaN を返します。  `printf` ファミリによる簡易な NaN の表現については、「[printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)」を参照してください。  
  
## 解説  
 `remainder` 関数は `x`\/`y` hidden と `x`\= `n` \*`y`\+`r` 浮動小数点の剰余  `n` が `x`\/`y` へ値に最も近いの整数である  `n` がたびにである `r` を計算し、&#124; `n` \- `x` \/ `y` &#124; \= 1\/2.  `r`に `x` と \= 0、`r` 同じ署名を持ちます。  
  
 C\+\+ ではオーバーロードが可能であるため、`float` または `long double` の値を受け取って返す `remainder` のオーバーロードを呼び出すことができます。  C プログラムでは、`remainder` .は 2 個の double を受け取り、常に Double を返します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`remainder`, `remainderf`, `remainderl`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```c  
// crt_remainder.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = remainder(w, x);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
}  
```  
  
  **\-10.00 \/ 3.00 の剰余は \-1.000000**   
## 同等の .NET Framework 関数  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ldiv、lldiv](../Topic/ldiv,%20lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod、fmodf](../Topic/fmod,%20fmodf.md)   
 [remquo、remquof、remquol](../Topic/remquo,%20remquof,%20remquol.md)