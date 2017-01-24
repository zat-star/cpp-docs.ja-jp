---
title: "nearbyint、nearbyintf、nearbyintl | Microsoft Docs"
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
  - "nearbyint"
  - "nearbyintf"
  - "nerabyintl"
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
  - "nearbyint"
  - "nearbyintf"
  - "nearbyintl"
  - "math/nearbyint"
  - "math/narbyintf"
  - "math/narbyintl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "nearbyint 関数"
  - "nearbyintf 関数"
  - "nearbyintl 関数"
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nearbyint、nearbyintf、nearbyintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定の浮動小数点値を整数に丸め、浮動小数点形式でその値を返します。  
  
## 構文  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 丸める値。  
  
## 戻り値  
 成功した場合、返す `x`, fegetround で定義されている現在の丸めの形式を使用して、最も近い整数に丸められた。 それ以外の場合、関数では、次の値のいずれかを返す可能性があります。  
  
|懸案事項|リターン|  
|----------|----------|  
|`x` ±INFINITY \=|±INFINITY、未変更の状態|  
|`x` \= ±0|±0、未変更の状態|  
|`x` \= NaN|NaN|  
  
 を通じてエラーは報告されません [\_matherr](../../c-runtime-library/reference/matherr.md)。 特に、この関数は、FE\_INEXACT 例外を報告しません。  
  
## 解説  
 この関数の主な違いと `rint` はこの関数では、不正確な浮動小数点例外は発生しません。  
  
 最大の浮動小数点値は正確な整数であるため、この関数がオーバーフローすることも、単独で代わりに、出力は、使用する関数のバージョンに応じて、戻り値をオーバーフローすることがあります。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`nearbyint`、`nearbyintf`、 `nearbyintl`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)