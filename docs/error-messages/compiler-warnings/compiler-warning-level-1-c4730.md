---
title: "コンパイラの警告 (レベル 1) C4730 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4730"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4730"
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4730
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'main' : \_m64 と浮動小数点式を混用することで、正しくないコードが発生する可能性があります。  
  
 関数で[\_\_m64](../../cpp/m64.md) 型と **float**\/**double** 型が使用されています。  MMX レジスタと浮動小数点レジスタは同じ物理レジスタ領域を共有していますが、この領域は同時に使用できないため、同じ関数の内部で `__m64` 型と **float**\/**double** 型を使用すると、データが破壊され、例外が発生する可能性があります。  
  
 安全に `__m64` の型と浮動小数点型を使用するには、型の使用が 1 **\_m\_empty\(\)** \(MMX の場合\) または **\_m\_femms\(\)** \(3DNow\!に組み込み\) で区切られた各命令手順機能します。  
  
 次の例では警告 C4730 が生成されます。  
  
```  
// C4730.cpp  
// compile with: /W1  
// processor: x86  
#include "mmintrin.h"  
  
void func(double)  
{  
}  
  
int main(__m64 a, __m64 b)  
{  
   __m64 m;  
   double f;  
   f = 1.0;  
   m = _m_paddb(a, b);  
   // uncomment the next line to resolve C4730  
   // _m_empty();  
   func(f * 3.0);   // C4730  
}  
```