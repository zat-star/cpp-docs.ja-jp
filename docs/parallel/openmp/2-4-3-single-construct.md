---
title: "2.4.3 single Construct | Microsoft Docs"
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
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.3 single Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**シングル**  のディレクティブは構造化のブロックはチーム \(\)マスター スレッドの 1 種類のスレッドによってのみ実行されるように指定する構造体を指定します。   **シングル**  のディレクティブの構文は次のとおりです :  
  
```  
#pragma omp single [clause[[,] clause] ...] new-line  
   structured-block  
```  
  
 句は次のいずれかです :  
  
 **\(プライベート**   *変数*  の  *リスト* **\)**  
  
 **\(firstprivate**  *変数*  の  *リスト* **\)**  
  
 **\(copyprivate**  *変数*  の  *リスト* **\)**  
  
 **nowait**  
  
 **nowait** の句の指定がない場合  **シングル**  の構造の後暗黙的なバリアがあります。  
  
 **シングル**  のディレクティブに制限 : は次のとおりです。  
  
-   **nowait** の一つの句だけ  **シングル**  のディレクティブで指定できます。  
  
-   **copyprivate** の句は **nowait** の句を使用しないでください。  
  
## cref:  
  
-   **プライベート  firstprivate** と **copyprivate** の句はページの 25 [セクション 2.7.2](../Topic/2.7.2%20Data-Sharing%20Attribute%20Clauses.md) が表示されます。