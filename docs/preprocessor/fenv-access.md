---
title: "fenv_access | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.fenv_access"
  - "fenv_access_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenv_access プラグマ"
  - "プラグマ, fenv_access"
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# fenv_access
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フラグ テストとモード変更を変える可能性のある最適化を無効 \(ON\) または有効 \(OFF\) にします。  
  
## 構文  
  
```  
#pragma fenv_access [ON | OFF]  
```  
  
## 解説  
 既定では、`fenv_access` は OFF です。  
  
 浮動小数点の動作の詳細については、「[\/fp \(浮動小数点の動作の指定\)](../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。  
  
 `fenv_access` の影響を受ける最適化の種類は次のとおりです。  
  
-   グローバルの共通部分式の削除  
  
-   コードの移動  
  
-   定数の折りたたみ  
  
 その他の浮動小数点プラグマには以下があります。  
  
-   [float\_control](../Topic/float_control.md)  
  
-   [fp\_contract](../preprocessor/fp-contract.md)  
  
## 使用例  
  
```  
// pragma_directive_fenv_access_x86.cpp  
// compile with: /O2  
// processor: x86  
#include <stdio.h>  
#include <float.h>   
#include <errno.h>  
#pragma fenv_access (on)  
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **out\=9.999999776482582e\-003**   
## 使用例  
 次のサンプルは、Itanium プロセッサ用の出力ファイルを作成するコンパイラ用です。  **\/fp:precise** は、中間結果を拡張精度で保持するため、FLT\_MAX \(3.402823466e\+38F\) よりも大きい値を計算でき、その結果として sum は、手動で計算した場合と同様に結果が 1.0 となります。  **\/fp:strict** は、ソース精度 \(float\) で中間結果を保持するため、最初の加算で無限大になり、式全体で無限大が維持されます。  
  
```  
// pragma_directive_fenv_access_IPF.cpp  
// compile with: /O2 /fp:precise  
// processor: IPF  
// compiling with /fp:precise prints 1.0F  
// compile with /fp:strict to print infinity  
  
#include <stdio.h>  
float arr[5] = {3.402823465e+38F,   
               3.402823462e+38F,  
               3.402823464e+38F,  
               3.402823463e+38F,  
               1.0F};  
  
int main() {  
   float sum = 0;  
   sum = arr[0] + arr[1] - arr[2] - arr[3] + arr[4];  
   printf_s("%f\n", sum);  
}  
```  
  
  **1.000000**   
## 使用例  
 前の例の `#pragma fenv_access (on)` をコメント アウトすると、コンパイラがコンパイル時に評価し、その場合、制御モードが使用されないため、出力が異なることに注意してください。  
  
```  
// pragma_directive_fenv_access_2.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>   
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **out\=1.000000000000000e\-002**   
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)