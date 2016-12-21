---
title: "コンパイラ エラー C3012 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3012"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3012"
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3012
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'intrinsic': 組み込み関数を、並行領域内で使用することはできません  
  
 [コンパイラ組み込み関数](../../intrinsics/compiler-intrinsics.md)は、`omp``parallel` 領域では使用できません。  
  
 次の例では C3012 が生成されます。  
  
```  
// C3012.cpp // compile with: /openmp #ifdef __cplusplus extern "C" { #endif void* _ReturnAddress(); #ifdef __cplusplus } #endif int main() { _ReturnAddress();   // OK #pragma omp parallel { _ReturnAddress();   // C3012 } }  
```