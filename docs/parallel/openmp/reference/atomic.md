---
title: "atomic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "atomic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atomic OpenMP directive"
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# atomic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

とをアトミックに更新されるメモリ位置指定します。  
  
## 構文  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### パラメーター  
 `expression`  
 ステートメント複数の書き込みに対する保護する左辺値のメモリ位置。  使用できる式の形式に関する詳細についてはOpenMP の仕様を参照してください。  
  
## 解説  
 `atomic` のディレクティブはOpenMP 句をサポートしていません。  
  
 詳細については、「[2.6.4 atomic Construct](../../../parallel/openmp/2-6-4-atomic-construct.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
  **スレッドの数 : 10**    
## 参照  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)