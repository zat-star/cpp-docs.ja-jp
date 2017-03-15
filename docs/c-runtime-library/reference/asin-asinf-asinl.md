---
title: "asin、asinf、asinl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "asinf"
  - "asinl"
  - "asin"
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
  - "asin"
  - "asinl"
  - "asinf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "arcsine 関数"
  - "asin 関数"
  - "asinf 関数"
  - "asinl 関数"
  - "三角関数"
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# asin、asinf、asinl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アークサインを計算します。  
  
## 構文  
  
```  
double asin(   
   double x   
);  
float asin(  
   float x  
);  // C++ only  
long double asin(  
   long double x  
);  // C++ only  
float asinf (   
   float x   
);  
long double asinl(  
   long double x  
);  
```  
  
#### パラメーター  
 `x`  
 アークサインが計算される値。  
  
## 戻り値  
 `asin` 関数は、\-π\/2 ～ π\/2 ラジアンの範囲で、`x` のアークサイン \(逆サイン関数\) を返します。  
  
 既定では、`x` が –1 未満または 1 よりも大きい場合、`asin` は不定値を返します。  
  
|入力|SEH 例外|Matherr 例外|  
|--------|------------|----------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± `QNAN`,`IND`|なし|`_DOMAIN`|  
|&#124;x&#124; \> 1|`INVALID`|`_DOMAIN`|  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` および `long double` で `asin` のオーバーロードを呼び出すことができます。  C プログラムでは、`asin` は常に double を受け取って返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`asin`, `asinf`, `asinl`|\<math.h\>|  
  
## 使用例  
 詳細については、「[acos、acosf、acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Math::Asin](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [acos、acosf、acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [atan、atanf、atanl、atan2、atan2f、atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos、cosf、cosl、cosh、coshf、coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan、tanf、tanl、tanh、tanhf、tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)