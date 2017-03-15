---
title: "fdim、fdimf、fdiml | Microsoft Docs"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
  - "math/fdim"
  - "math/fdimf"
  - "math/fdiml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fdim 関数"
  - "fdimf 関数"
  - "fdiml 関数"
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# fdim、fdimf、fdiml
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

番目と 2 番目の値の正の値の差を決定します。  
  
## 構文  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 最初の値。  
  
 \[入力\] `y`  
 2 番目の値。  
  
## 戻り値  
 正の値の差を返します `x` と `y`:  
  
|戻り値|シナリオ|  
|---------|----------|  
|x と y|場合 x \> y|  
|0|場合 x \< \= y|  
  
 それ以外の場合を返す、次のエラーのいずれか。  
  
|懸案事項|リターン|  
|----------|----------|  
|オーバーフロー エラーの範囲|\+ HUGE\_VAL、\+ HUGE\_VALF、または \+ なります。|  
|アンダー フロー範囲エラー|正しい値 \(丸めた\)|  
|`x` または `y` nan|NaN|  
  
 エラーが報告されるの説明に従って [\_matherr](../../c-runtime-library/reference/matherr.md)します。  
  
## 解説  
 オーバー ロードを呼び出すことができますので、C ではオーバー ロード、 `fdim` を受け取り、float 型と long double 型を返します。 C プログラムでは、`fdim` は常に double を受け取って返します。  
  
 この関数は NaN 処理を除くと同じで、 [fmax、fmaxf、fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)\(`x`\-`y,` 0\)。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`fdim`、`fdimf`、 `fdiml`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmax、fmaxf、fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [abs、labs、llabs、\_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)