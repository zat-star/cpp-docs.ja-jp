---
title: "default (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default OpenMP clause"
  - "defaults, OpenMP clause"
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# default (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

並列領域で unscoped 変数の動作を指定します。  
  
## 構文  
  
```  
default(shared | none)  
```  
  
## 解説  
 `shared` が有効である `default` 句で指定されていない場合 [shared](../../../parallel/openmp/reference/shared-openmp.md) の句で指定されている並列領域内の変数は処理されることを意味します。  `none` は並列領域 [shared](../../../parallel/openmp/reference/shared-openmp.md)[reduction](../../../parallel/openmp/reference/reduction.md)[firstprivate](../Topic/firstprivate.md)または [lastprivate](../../../parallel/openmp/reference/lastprivate.md) の句で使用する [private](../../../parallel/openmp/reference/private-openmp.md) としてスコープの変数を指定するとコンパイラ エラーが発生することを意味します。  
  
 `default` は次のディレクティブに対象 :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、「[2.7.2.5 default](../../../parallel/openmp/2-7-2-5-default.md)」を参照してください。  
  
## 使用例  
 `default` 使用例については[private](../../../parallel/openmp/reference/private-openmp.md) を参照してください。  
  
## 参照  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)