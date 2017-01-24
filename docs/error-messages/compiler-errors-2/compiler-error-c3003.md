---
title: "コンパイラ エラー C3003 | Microsoft Docs"
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
  - "C3003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3003"
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'directive': OpenMP ディレクティブ名は、ディレクティブ句の後には使用できません  
  
 OpenMP ディレクティブの名前は、OpenMP ディレクティブの句の後に続けることはできません。  
  
 次の例では C3003 が生成されます。  
  
```  
// C3003.c // compile with: /openmp int main() { int x, y, z; #pragma omp parallel shared(x, y, z) for   // C3003 }  
```