---
title: "copysign、copysignf、copysignl、_copysign、_copysignf、_copysignl | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "copysignf"
  - "copysignl"
  - "_copysignl"
  - "_copysign"
  - "_copysignf"
  - "copysign"
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
  - "_copysignl"
  - "copysign"
  - "copysignf"
  - "_copysign"
  - "copysignl"
  - "_copysignf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_copysign 関数"
  - "_copysignf 関数"
  - "_copysignl 関数"
  - "copysign 関数"
  - "copysignf 関数"
  - "copysignl 関数"
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# copysign、copysignf、copysignl、_copysign、_copysignf、_copysignl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ある引数の絶対値と別の引数の符号を持つ値を返します。  
  
## 構文  
  
```  
double copysign(   
   double x,  
   double y   
);  
float copysign(   
   float x,  
   float y   
); // C++ only  
long double copysign(   
   long double x,  
   long double y   
); // C++ only  
float copysignf(   
   float x,  
   float y   
); // C++ only  
long double copysignl(   
   long double x,  
   long double y   
); // C++ only  
double _copysign(   
   double x,  
   double y   
);  
long double _copysignl(   
   long double x,  
   long double y   
);  
```  
  
#### パラメーター  
 `x`  
 結果の絶対値として返される浮動小数点値。  
  
 `y`  
 結果の符号として返される浮動小数点値。  
  
 [浮動小数点サポート ルーチン](../../c-runtime-library/floating-point-support.md)  
  
## 戻り値  
 `copysign` は、`x` の絶対値と `y` の符号を組み合わせた浮動小数点値を返します。  エラーの戻り値はありません。  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` または `long double` の値を受け取って返す `copysign` のオーバーロードを呼び出すことができます。  C プログラムでは、`copysign` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_copysign`|\<float.h\>|  
|`copysign`, `copysignf`, `copysignl`, `_copysignf` `_copysignl`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [fabs、fabsf、fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [\_chgsign、\_chgsignf、\_chgsignl](../../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)