---
title: "cos、cosf、cosl、cosh、coshf、coshl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "coshl"
  - "cosh"
  - "cos"
  - "cosl"
  - "cosf"
  - "coshf"
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
  - "coshl"
  - "cos"
  - "cosf"
  - "cosh"
  - "cosl"
  - "coshf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "計算 (コサインを)"
  - "cos 関数"
  - "cosf 関数"
  - "cosh 関数"
  - "coshf 関数"
  - "coshl 関数"
  - "コサイン"
  - "コサイン, 計算"
  - "cosl 関数"
  - "ハイパーボリック関数"
  - "三角関数"
ms.assetid: ae90435e-6b68-4a47-a81f-be87d5c08f16
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# cos、cosf、cosl、cosh、coshf、coshl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コサイン \(`cos`、`cosf`、または `cosl`\)、またはハイパーボリック コサイン \(`cosh`、`coshf`、または `coshl`\) を計算します。  
  
## 構文  
  
```  
double cos(   
   double x   
);  
float cos(  
   float x   
);  // C++ only  
long double cos(  
   long double x  
);  // C++ only  
float cosf(   
   float x   
);  
long double cosl(  
   long double x  
);  
double cosh(   
   double x   
);  
float cosh(  
   float x   
);  // C++ only  
long double cosh(  
   long double x  
);  // C++ only  
float coshf(  
   float x   
);  
long double coshl(  
   long double x  
);  
```  
  
#### パラメーター  
 `x`  
 角度 \(ラジアン\)。  
  
## 戻り値  
 `x` のコサインまたはハイパーボリック コサイン。  `x` が 263 以上、または –263 以下の場合、`cos`、`cosf`、`cosl` の呼び出しの結果から有意性が失われます。  
  
 既定では、`cosh`、`coshf`、または `coshl` の呼び出しで結果が大きすぎる場合、関数は `HUGE_VAL` を返し、`errno` に `ERANGE` を設定します。  
  
|入力|SEH 例外|Matherr 例外|  
|--------|------------|----------------|  
|± `QNAN`,`IND`|なし|`_DOMAIN`|  
|± ∞  \(`cosf`, `cos`, `cosl`\)|`INVALID`|`_DOMAIN`|  
|x ≥ 7.104760e\+002  \(`cosh`、`coshf`、`coshl`\)|`INEXACT`\+`OVERFLOW`|`OVERFLOW`|  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` または `long double` の値を受け取って返す `cos` および `cosh` のオーバーロードを呼び出すことができます。  C プログラムでは、`cos` および `cosh` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`cos`, `cosh`, `cosf`, `coshf`, `cosl`, `coshl`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md) の例を参照してください。  
  
## 同等の .NET Framework 関数  
  
-   [System::Math::Cos](https://msdn.microsoft.com/en-us/library/system.math.cos.aspx)  
  
-   [System::Math::Cosh](https://msdn.microsoft.com/en-us/library/system.math.cosh.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [acos、acosf、acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin、asinf、asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan、atanf、atanl、atan2、atan2f、atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan、tanf、tanl、tanh、tanhf、tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CIcos](../../c-runtime-library/cicos.md)