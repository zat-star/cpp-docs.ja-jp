---
title: "ilogb、ilogbf、ilogbl | Microsoft Docs"
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
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
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
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
  - "math/ilogb"
  - "math/ilogbf"
  - "math/ilogbl"
helpviewer_keywords: 
  - "ilogb 関数"
  - "ilogbf 関数"
  - "ilogbl 関数"
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ilogb、ilogbf、ilogbl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定した値のバイアスをかけない 2 を底と指数を表す整数値を取得します。  
  
## 構文  
  
```  
int ilogb(  
   double x  
);  
  
int ilogb(  
   float x  
); //C++ only  
  
int ilogb(  
   long double x  
); //C++ only  
  
int ilogbf(  
   float x  
);  
  
int ilogbl(  
   long double x  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 指定した値。  
  
## 戻り値  
 成功した場合の 2 を底と指数部を返す `x` 符号付きとして `int` 値。  
  
 それ以外の場合、\< math.h \> で定義されている、次の値のいずれかを返します。  
  
|入力|結果|  
|--------|--------|  
|±0|FP\_ILOGB0|  
|±inf ±nan、不定値|FP\_ILOGBNAN|  
  
 エラーが報告されるの説明に従って [\_matherr](../../c-runtime-library/reference/matherr.md)します。  
  
## 解説  
 オーバー ロードを呼び出すことができますので、C ではオーバー ロード、 `ilogb` を受け取り、float 型と long double 型を返します。 C プログラムでは、`ilogb` は常に double を受け取って返します。  
  
 この関数を呼び出すことは、それと同等の呼び出しに似ています `logb` 関数への戻り値をキャスト `int`します。  
  
## 必要条件  
  
|ルーチン|C ヘッダー|C\+\+ ヘッダー|  
|----------|------------|----------------|  
|`ilogb`、`ilogbf`、 `ilogbl`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [logb、logbf、logbl、\_logb、\_logbf](../../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)