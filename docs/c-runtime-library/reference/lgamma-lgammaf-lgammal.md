---
title: "lgamma、lgammaf、lgammal | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "lgamma"
  - "lgammaf"
  - "lgammal"
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
  - "lgamma"
  - "lgammaf"
  - "lgammal"
  - "math/lgamma"
  - "math/lgammaf"
  - "math/lgammal"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "lgamma 関数"
  - "lgammal 関数"
  - "lgammaf 関数"
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# lgamma、lgammaf、lgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定した値のガンマ関数の絶対値の自然対数を決定します。  
  
## 構文  
  
```  
double lgamma(  
   double x  
);  
  
float lgamma(  
   float x  
); //C++ only  
  
long double lgamma(  
   long double x  
); //C++ only  
  
float lgammaf(  
   float x  
);  
  
long double lgammal(  
   long double x  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 計算する値。  
  
## 戻り値  
 成功した場合、値のガンマ関数の絶対値の自然対数を返す `x.`  
  
|懸案事項|リターン|  
|----------|----------|  
|`x` \= NaN|NaN|  
|`x` \= ±0|\+ INFINITY|  
|`x`負の整数を \=|\+ INFINITY|  
|±INFINITY|\+ INFINITY|  
|極エラー|\+ HUGE\_VAL、\+ HUGE\_VALF、または \+ なります。|  
|オーバーフロー エラーの範囲|±HUGE\_VAL、±HUGE\_VALF、または ±HUGE\_VALL|  
  
 エラーが報告されるの説明に従って [\_matherr](../../c-runtime-library/reference/matherr.md)します。  
  
## 解説  
 オーバー ロードを呼び出すことができますので、C ではオーバー ロード、 `lgamma` を受け取り、float 型と long double 型を返します。 C プログラムでは、`lgamma` は常に double を受け取って返します。  
  
 この関数が数値の階乗の対数を返します x が、有理数の場合は、\(`x`\-1\)。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`lgamma`、`lgammaf`、 `lgammal`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [tgamma、tgammaf、tgammal](../../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)