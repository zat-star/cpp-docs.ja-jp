---
title: "exp2、exp2f、exp2l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "exp2"
  - "exp2f"
  - "exp2l"
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
  - "exp2"
  - "math/exp2"
  - "exp2f"
  - "math/exp2f"
  - "exp2l"
  - "math/exp2l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exp2 関数"
  - "exp2f 関数"
  - "exp2l 関数"
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# exp2、exp2f、exp2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2 乗 \(つまり、2ˣ\) の指定した値を計算します。  
  
## 構文  
  
```  
double exp2(  
   double x  
);  
  
float exp2(  
   float x  
);  // C++ only  
  
long double exp2(  
   long double x  
); // C++ only  
  
float exp2f(  
   float x  
);  
  
long double exp2l(  
   long double x  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 指数部の値です。  
  
## 戻り値  
 成功した場合の 2 を底と指数を返します `x` \(2ˣ\)。 それ以外の場合を返す、次の値のいずれか。  
  
|懸案事項|リターン|  
|----------|----------|  
|`x` \= ±0|1|  
|`x` \= \- 無限大|\+0|  
|`x` \= \+ INFINITY|\+ INFINITY|  
|`x` \= NaN|NaN|  
|オーバーフロー エラーの範囲|\+ HUGE\_VAL、\+ HUGE\_VALF、または \+ なります。|  
|アンダー フロー範囲エラー|丸めたの正しい結果|  
  
 エラーが報告されるの説明に従って [\_matherr](../../c-runtime-library/reference/matherr.md)します。  
  
## 解説  
 オーバー ロードを呼び出すことができますので、C ではオーバー ロード、 `exp2` を受け取り、float 型と long double 型を返します。 C プログラムでは、`exp2` は常に double を受け取って返します。  
  
## 必要条件  
  
|ルーチン|C ヘッダー|C\+\+ ヘッダー|  
|----------|------------|----------------|  
|`exp`、`expf`、`expl`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp、expf](../../c-runtime-library/reference/exp-expf.md)   
 [log2、log2f、log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)