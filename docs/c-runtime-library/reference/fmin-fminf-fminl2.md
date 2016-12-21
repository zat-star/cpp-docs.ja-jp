---
title: "fmin、fminf、fminl | Microsoft Docs"
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
  - "fmin"
  - "fminf"
  - "fminl"
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
  - "fmin"
  - "fminf"
  - "fminl"
  - "math/fmin"
  - "math/fminf"
  - "math/fminl"
helpviewer_keywords: 
  - "fmin 関数"
  - "fminf 関数"
  - "fminl 関数"
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fmin、fminf、fminl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された 2 つの値のいずれか小さい方を決定します。  
  
## 構文  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
  
```  
  
#### パラメーター  
 `x`  
 比較する最初の値です。  
  
 `y`  
 比較する 2 番目の値です。  
  
## 戻り値  
 成功した場合、取得のうち、小さい方 `x` または `y`です。  
  
|入力|結果|  
|--------|--------|  
|`x` nan します。|`y`|  
|`y` nan します。|`x`|  
|`x` `y` nan|nan|  
  
 この関数は伴いません [\_matherr](../../c-runtime-library/reference/matherr.md) 呼び出される浮動小数点の例外が発生するかの値を変更 `errno`します。  
  
## 解説  
 オーバー ロードを呼び出すことができますので、C ではオーバー ロード、 `fmin` を受け取り、float 型と long double 型を返します。 C プログラムでは、`fmin` は常に double を受け取って返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`fmin`、`fminf`、 `fminl`|C: \< math.h \><br /><br /> C\+\+ の場合: \< math.h \> または \< cmath \>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)