---
title: "fma、fmaf、fmal | Microsoft Docs"
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
  - "fma"
  - "fmaf"
  - "fmal"
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
  - "fma"
  - "fmaf"
  - "fmal"
  - "math/fma"
  - "math/fmaf"
  - "math/fmal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fma 関数"
  - "fmaf 関数"
  - "fmal 関数"
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# fma、fmaf、fmal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2 つの値を乗算、3 番目の値を追加し、中間丸め処理を行うための有効桁数を失うことがなく、結果を丸めます。  
  
## 構文  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### パラメーター  
 \[入力\] `x`  
 乗算する 1 番目の値。  
  
 \[入力\] `y`  
 乗算する 2 番目の値。  
  
 \[入力\] `z`  
 加算する値。  
  
## 戻り値  
 Returns \(`x` ×    `y`\) \+ `z`. 戻り値には、現在の丸めの形式を使用して、丸められます。  
  
 それ以外の場合を返す、次の値のいずれか。  
  
|懸案事項|リターン|  
|----------|----------|  
|`x` \= 無限大 `y` \= 0、または<br /><br /> `x` \= 0、 `y` 無限大|NaN|  
|`x` または `y` \= 正確な ± の無限大、 `z` 無限大逆の符号|NaN|  
|`x` または `y` \= NaN|NaN|  
|されません \(`x` \= 0、 `y`\= 無制限\) と `z` \= NaN<br /><br /> されません \(`x`\= 不定値、 `y`\= 0\) と `z` \= NaN|NaN|  
|オーバーフロー エラーの範囲|±HUGE\_VAL、±HUGE\_VALF、または ±HUGE\_VALL|  
|アンダー フロー範囲エラー|丸め処理後の適切な値。|  
  
 エラーが報告されるの説明に従って [\_matherr](../../c-runtime-library/reference/matherr.md)します。  
  
## 解説  
 オーバー ロードを呼び出すことができますので、C ではオーバー ロード、 `fma` を受け取り、float 型と long double 型を返します。 C プログラムでは、`fma` は常に double を受け取って返します。  
  
 この関数は、無限の精度を行った、最終的な結果を丸める場合と同様に、値を計算します。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`fma`、`fmaf`、 `fmal`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder、remainderf、remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo、remquof、remquol](../Topic/remquo,%20remquof,%20remquol.md)