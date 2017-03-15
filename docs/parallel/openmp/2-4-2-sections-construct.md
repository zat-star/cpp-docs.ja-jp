---
title: "2.4.2 sections Construct | Microsoft Docs"
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
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.2 sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**セクション**  のディレクティブはチームのスレッドで除算一連の構造体を指定する noniterative 作業共有の構造体を指定します。  各セクションはチームのスレッドによって回実行されます。   **セクション**  のディレクティブの構文は次のとおりです :  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block ]  
...  
}  
```  
  
 句は次のいずれかです :  
  
 **\(プライベート**   *変数*  の  *リスト* **\)**  
  
 **\(firstprivate**  *変数*  の  *リスト* **\)**  
  
 **\(lastprivate**  *変数*  の  *リスト* **\)**  
  
 **\(縮小**  の  *演算子の* **:**  *変数*  の  *リスト* **\)**  
  
 **nowait**  
  
 各セクションは  **セクション**  のディレクティブに  **セクション**  のディレクティブが最初のセクションについては省略可能ですが継続されます。   **セクション**  のディレクティブはディレクティブの構文  **セクション**  の範囲で囲みます。  **nowait** が指定されていない場合 **セクション**  構造体の最後に暗黙的なバリアがあります。  
  
 **セクション**  のディレクティブに制限 : は次のとおりです。  
  
-   **セクション**  のディレクティブはディレクティブの構文  **セクション**  の範囲外で表示する必要があります。  
  
-   **nowait** の一つの句だけ  **セクション**  のディレクティブで指定できます。  
  
## cref:  
  
-   **プライベート  firstprivate lastprivate** と  **リダクション**  の句はページの 25 [セクション 2.7.2](../Topic/2.7.2%20Data-Sharing%20Attribute%20Clauses.md) が表示されます。