---
title: "fmax、fmaxf、fmaxl | Microsoft Docs"
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
  - "fmax"
  - "fmaxf"
  - "fmaxl"
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
  - "fmax"
  - "fmaxf"
  - "fmaxl"
  - "math/fmax"
  - "math/fmaxf"
  - "math/fmaxl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fmax 関数"
  - "fmaxf 関数"
  - "fmaxl 関数"
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# fmax、fmaxf、fmaxl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定した 2 つの数値のうち、大きい方を決定します。  
  
## 構文  
  
```  
double fmax(  
   double x,   
   double y  
);  
  
float fmax(  
   float x,   
   float y  
); //C++ only  
  
long double fmax(  
   long double x,   
   long double y  
); //C++ only  
  
float fmaxf(  
   float x,   
   float y  
);  
  
long double fmaxl(  
   long double x,   
   long double y  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 比較する最初の値です。  
  
 \[入力\] `y`  
 比較する 2 番目の値です。  
  
## 戻り値  
 成功した場合のうち、大きい方を返します `x` または `y`です。 返される値は厳密であり、なんらかの丸め処理を行うには依存しません。  
  
 それ以外の場合を返す、次の値のいずれか。  
  
|懸案事項|リターン|  
|----------|----------|  
|`x` \= NaN|`y`|  
|`y` \= NaN|`x`|  
|`x` `y` \= NaN|NaN|  
  
 この関数がで指定されたエラーを使用しない  [\_matherr](../../c-runtime-library/reference/matherr.md)します。  
  
## 解説  
 C\+\+ ではオーバー ロードであるためにを実行し、float、long double 型 fmax のオーバー ロードを呼び出すことができます。 C プログラムでは fmax は常に取得し、double 型の値を返します。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`fmax`、`fmaxf`、`fmaxl`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmin, fminf, fminl](../Topic/fmin,%20fminf,%20fminl1.md)