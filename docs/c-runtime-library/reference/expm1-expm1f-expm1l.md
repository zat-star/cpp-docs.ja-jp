---
title: "expm1、expm1f、expm1l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "expm1l"
  - "expm1"
  - "expm1f"
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
  - "expm1l"
  - "expm1"
  - "expm1f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expm1 関数"
  - "expm1f 関数"
  - "expm1l 関数"
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# expm1、expm1f、expm1l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

e を底とする値のべき乗から 1 を引く計算を行います。  
  
## 構文  
  
```  
double expm1(   
   double x   
);  
float expm1(  
   float x  
);  // C++ only  
long double expm1(  
   long double x  
);  // C++ only  
float expm1f(  
   float x  
);  
long double expm1l(  
   long double x  
);  
```  
  
#### パラメーター  
 `x`  
 浮動小数点の指数値。  
  
## 戻り値  
 `expm1` 関数は、正常に終了した場合、e<sup>x</sup> – 1 を表す浮動小数点値を返します。  オーバーフローが発生すると、`expm1` は `HUGE_VAL` を返し、`expm1f` は `HUGE_VALF` を返し、`expm1l` は `HUGE_VALL` を返します。`errno` は `ERANGE` に設定されます。  リターン コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` および `long double` の値を受け取って返す `expm1` のオーバーロードを呼び出すことができます。  C プログラムでは、`expm1` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`expm1`, `expm1f`, `expm1l`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [exp2、exp2f、exp2l](http://msdn.microsoft.com/ja-jp/a7974629-be1e-4196-a562-6624a0732003)   
 [pow、powf、powl](../Topic/pow,%20powf,%20powl.md)