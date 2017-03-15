---
title: "trunc、truncf、truncl | Microsoft Docs"
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
  - "trunc"
  - "truncf"
  - "truncl"
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
  - "trunc"
  - "truncf"
  - "truncl"
  - "math/trunc"
  - "math/truncf"
  - "math/truncl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "trunc 関数"
  - "truncf 関数"
  - "truncl 関数"
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# trunc、truncf、truncl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された浮動小数点値以下である最も近い整数を指定します。  
  
## 構文  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 切り捨てる値です。  
  
## 戻り値  
 成功した場合、整数値が返されます `x`, 0 方向に丸められた。  
  
 それ以外の場合を返す、次のいずれか。  
  
|懸案事項|リターン|  
|----------|----------|  
|`x` ±INFINITY \=|x|  
|`x` \=  ±0|x|  
|`x` \= NaN|NaN|  
  
 エラーが報告されるの説明に従って [\_matherr](../../c-runtime-library/reference/matherr.md)します。  
  
## 解説  
 オーバー ロードを呼び出すことができますので、C ではオーバー ロード、 `trunc` を受け取り、float 型と long double 型を返します。 C プログラムでは、`trunc` は常に double を受け取って返します。  
  
 浮動小数点数の最大値は正確な整数であるため、この関数は単独ではオーバーフローできません。 ただし、整数型に値を返すことによってオーバーフローが発生する関数が発生する可能性があります。  
  
 浮動小数点から整数; への暗黙的に変換しても切り捨てることができます。ただし、この作業は、対象の型に格納できる値に制限です。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`trunc`、`truncf`、 `truncl`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [floor、floorf、floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [ceil、ceilf、ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round、roundf、roundl](../../c-runtime-library/reference/round-roundf-roundl.md)