---
title: "erf、erff、erfl、erfc、erfcf、erfcl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "erff"
  - "erfl"
  - "erf"
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
  - "erfl"
  - "erf"
  - "erff"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erf 関数"
  - "erff 関数"
  - "erfl 関数"
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# erf、erff、erfl、erfc、erfcf、erfcl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

値の誤差関数または相補誤差関数を計算します。  
  
## 構文  
  
```  
double erf(    double x ); float erf(    float x ); // C++ only long double erf(    long double x ); // C++ only float erff(    float x ); long double erfl(    long double x ); double erfc(    double x ); float erfc(    float x ); // C++ only long double erfc(    long double x ); // C++ only float erfcf(    float x ); long double erfcl(    long double x );  
```  
  
#### パラメーター  
 `x`  
 浮動小数点値。  
  
## 戻り値  
 `erf` 関数は、`x` のガウスの誤差関数を返します。  `erfc` 関数は、`x` のガウスの相補誤差関数を返します。  
  
## 解説  
 `erf` 関数は、次のように定義されているガウスの誤差関数を計算します。  
  
 ![x の誤差関数](../../c-runtime-library/reference/media/crt_erf_formula.png "CRT\_erf\_formula")  
  
 ガウスの相補誤差関数は、1 – erf\(x\) と定義されています。  `erf` 関数は、\-1.0 ～ 1.0 の範囲の値を返します。  エラーの戻り値はありません。  `erfc` 関数は、0 ～ 2 の範囲の値を返します。  `x` が `erfc` に対して大きすぎる場合、`errno` 変数は `ERANGE` に設定されます。  
  
 C\+\+ ではオーバーロードが可能であるため、`float` 型と `long double` 型を受け取って返す `erf` と `erfc` のオーバーロードを呼び出すことができます。  C プログラムでは、`erf` および `erfc` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`erf`, `erff`, `erfl`, `erfc`, `erfcf`, `erfcl`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)