---
title: "fp_contract | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.fp_contract"
  - "fp_contract_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fp_contract プラグマ"
  - "プラグマ, fp_contract"
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# fp_contract
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

浮動小数点の縮約が発生したかを判定します。  
  
## 構文  
  
```  
#pragma fp_contract [ON | OFF]  
```  
  
## 解説  
 `fp_contract` は既定でオンになります。  
  
 浮動小数点の動作の詳細については、「[\/fp \(浮動小数点の動作の指定\)](../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。  
  
 その他の浮動小数点プラグマには以下があります。  
  
-   [fenv\_access](../preprocessor/fenv-access.md)  
  
-   [float\_control](../Topic/float_control.md)  
  
## 使用例  
 このサンプルから生成されるコードは、Itanium プロセッサ上で融合型積和演算 \(**fma**: Fused Multiply Add\) 命令を使用しません。  `#pragma fp_contract (off)` をコメント アウトすると、生成されたコードでは **fma** 命令が使用されます。  
  
```  
// pragma_directive_fp_contract.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>  
  
#pragma fp_contract (off)   
  
int main() {  
   double z, b, t;  
  
   for (int i = 0; i < 10; i++) {  
      b = i * 5.5;  
      t = i * 56.025;  
      _set_controlfp(_PC_24, _MCW_PC);  
  
      z = t * i + b;  
      printf_s ("out=%.15e\n", z);  
   }  
}  
```  
  
  **out\=0.000000000000000e\+000**  
**out\=6.152500152587891e\+001**  
**out\=2.351000061035156e\+002**  
**out\=5.207249755859375e\+002**  
**out\=9.184000244140625e\+002**  
**out\=1.428125000000000e\+003**  
**out\=2.049899902343750e\+003**  
**out\=2.783724853515625e\+003**  
**out\=3.629600097656250e\+003**  
**out\=4.587524902343750e\+003**   
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)