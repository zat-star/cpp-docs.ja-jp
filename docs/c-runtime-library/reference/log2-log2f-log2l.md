---
title: "log2、log2f、log2l | Microsoft Docs"
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
  - "log2"
  - "log2l"
  - "log2f"
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
dev_langs: 
  - "C"
  - "C++"
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# log2、log2f、log2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定した値のバイナリ \(基本 2\) 対数を決定します。  
  
## 構文  
  
```  
double log2(  
   double x  
);  
  
float log2(  
   float x  
); //C++ only  
  
long double log2(  
   long double x  
); //C++ only  
  
float log2f(  
   float x  
);  
  
long double log2l(  
   long double x  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 2 を底とする対数を決定する値。  
  
## 戻り値  
 成功した場合、戻り値が返さ log2 `x`します。  
  
 それ以外の場合を返す、次の値のいずれか。  
  
|懸案事項|リターン|  
|----------|----------|  
|`x` \< 0|NaN|  
|`x` \= ±0|\-無限大|  
|`x` \= 1|\+0|  
|\+ INFINITY|\+ INFINITY|  
|NaN|NaN|  
|ドメイン エラー|NaN|  
|極エラー|\-HUGE\_VAL、HUGE\_VALF となります。|  
  
 エラーが報告されるの説明に従って [\_matherr](../../c-runtime-library/reference/matherr.md)します。  
  
## 解説  
 この関数は基本的の最上位 1 ビットの 0 から始まるインデックスを返します x が整数である場合は、 `x`です。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`log2`、`log2f`、 `log2l`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp2、exp2f、exp2l](../../c-runtime-library/reference/exp2-exp2f-exp2l.md)   
 [log、logf、log10、log10f](../Topic/log,%20logf,%20log10,%20log10f.md)