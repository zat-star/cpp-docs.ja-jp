---
title: "コンパイラ エラー C3047 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3047"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3047"
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3047
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP 'sections' 領域の構造化ブロックの前には '\#pragma omp section' が必要です  
  
 [セクション](../../parallel/openmp/reference/sections-openmp.md) ディレクティブによって導入されるコード ブロック内のすべてのコードは、`section` ディレクティブによって導入されるコード ブロック内にある必要があります。  
  
 次の例では C3047 が生成されます。  
  
```  
// C3047.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections { #pragma omp section { ++n3; } ++n2;   // C3047 not enclosed in #pragma omp section } } }  
```