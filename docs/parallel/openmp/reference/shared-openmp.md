---
title: "shared (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Shared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared OpenMP clause"
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# shared (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

一つ以上の変数がすべてのスレッドで共有されることを指定します。  
  
## 構文  
  
```  
shared(var)  
```  
  
## 解説  
 指定項目  
  
 `var`  
 1 つ共有する別の変数。  複数の変数を指定する場合はコンマで区切ります。変数名。  
  
## 解説  
 スレッド間で共有するもう一つの方法は[copyprivate](../Topic/copyprivate.md) の句を使用します。  
  
 `shared` は次のディレクティブに対象 :  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、「[2.7.2.4 shared](../../../parallel/openmp/2-7-2-4-shared.md)」を参照してください。  
  
## 使用例  
 `shared` 使用例については[private](../../../parallel/openmp/reference/private-openmp.md) を参照してください。  
  
## 参照  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)