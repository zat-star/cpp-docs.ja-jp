---
title: "2.5.2 parallel sections Construct | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.5.2 parallel sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**並列セクション**  のディレクティブは  **セクション**  の一つのディレクティブだけを含む  **並列**  領域を指定するためのフォームへのショートカットを提供します。  セマンティクスは明示的にすぐに  **セクション**  のディレクティブに続く  **並列**  のディレクティブを指定することと同じです。   **並列セクション**  のディレクティブの構文は次のとおりです :  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block  ]  
   ...  
}  
```  
  
 *句は*  **nowait** の句以外  **並列**  と  **セクション**  のディレクティブによって使用される句の 1 つです。  
  
## cref:  
  
-   **並列**  のディレクティブはページの 8. [セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) が表示されます。  
  
-   **セクション**  のディレクティブはページの 14 [セクション 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) が表示されます。