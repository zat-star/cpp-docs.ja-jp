---
title: "fpclassify | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fpclassify"
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
apitype: "HeaderDef"
f1_keywords: 
  - "fpclassify"
  - "math/fpclassify"
helpviewer_keywords: 
  - "fpclassify マクロ"
  - "fpclassify 関数"
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fpclassify
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数の浮動小数点の分類を返します。  
  
## 構文  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### パラメーター  
 `x`  
 テストする浮動小数点値。  
  
## 戻り値  
 `fpclassify` 引数の浮動小数点クラスを示す整数値を返す `x`します。 によって返される有効な値を表 `fpclassify`, \< math.h \> に定義されている。  
  
|値|説明|  
|-------|--------|  
|`FP_NAN`|サイレント モード、シグナル、または不確定な NaN|  
|`FP_INFINITE`|正または負の無限大|  
|`FP_NORMAL`|正または負正規化された 0 でない値|  
|`FP_SUBNORMAL`|正または負の値が非正規化|  
|`FP_ZERO`|正または負のゼロ値|  
  
## 解説  
 C では、 `fpclassify` マクロです。 C\+\+ では、 `fpclassify` の引数の型を使用するオーバー ロードされた関数は、 `float`, 、`double`, 、または `long double`です。 どちらの場合に返される値は、中間表記ではなく、引数式の有効な型に依存します。 たとえば、通常 `double` または `long double` 値は、無限になる、denormal、またはゼロ値に変換すると、 `float`です。  
  
## 必要条件  
  
|関数とマクロ|必須ヘッダー \(C\)|必須ヘッダー \(C\+\+\)|  
|------------|------------------|----------------------|  
|`fpclassify`|\<math.h\>|\<math.h\> または \<cmath\>|  
  
 `fpclassify` マクロと `fpclassify` 関数は、C99 および c\+\+ 11 仕様に準拠しています。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [isnan、\_isnan、\_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)