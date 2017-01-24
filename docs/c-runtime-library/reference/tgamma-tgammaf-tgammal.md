---
title: "tgamma、tgammaf、tgammal | Microsoft Docs"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
  - "math/tgamma"
  - "math/tgammaf"
  - "math/tgammal"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "tgamma 関数"
  - "tgammaf 関数"
  - "tgammal 関数"
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tgamma、tgammaf、tgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定した値のガンマ関数を決定します。  
  
## 構文  
  
```  
double tgamma(  
   double x  
);  
  
float tgamma(  
   float x  
); //C++ only  
  
long double tgamma(  
   long double x  
); //C++ only  
  
float tgammaf(  
   float x  
);  
  
long double tgammal(  
   long double x  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 ガンマ値を検索する値。  
  
## 戻り値  
 成功した場合、取得のガンマ `x`します。  
  
 場合に、範囲エラーが発生する可能性がありますの大きさ `x` 大きすぎるか小さすぎるため、データ型。 場合に、ドメイン エラーまたは範囲エラーが発生する `x` \< \= 0。  
  
|懸案事項|リターン|  
|----------|----------|  
|x \= ±0|±INFINITY|  
|x \= 負の整数|NaN|  
|x \= \- 無限大|NaN|  
|x \= \+ INFINITY|\+ INFINITY|  
|x \= NaN|NaN|  
|ドメイン エラー|NaN|  
|極エラー|±HUGE\_VAL、±HUGE\_VALF、または ±HUGE\_VALL|  
|オーバーフロー エラーの範囲|±HUGE\_VAL、±HUGE\_VALF、または ±HUGE\_VALL|  
|アンダー フロー範囲エラー|丸めた正しい値です。|  
  
 エラーが報告されるの説明に従って [\_matherr](../../c-runtime-library/reference/matherr.md)します。  
  
## 解説  
 C\+\+ ではオーバー ロードであるためにを実行し、float、long double 型 tgamma のオーバー ロードを呼び出すことができます。 C プログラムでは tgamma は常に取得し、double 型の値を返します。  
  
 X が自然数の場合は、この関数は、\(x\-1\) の階乗を返します。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`tgamma`、`tgammaf`、 `tgammal`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [lgamma、lgammaf、lgammal](../../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)