---
title: "4.1 OMP_SCHEDULE | Microsoft Docs"
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
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.1 OMP_SCHEDULE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_SCHEDULE** は **For**およびスケジュールの型  **ランタイム**  がある  **並列の**  のディレクティブにのみ適用されます。  このようなすべてのループのスケジュールの型とチャンクのサイズは実行時に認識されたスケジュールの型のいずれかにこの環境変数を設定してで設定できオプションのに *chunk\_size*。  
  
 **For** およびスケジュール  **ランタイム**  以外の型を持つ  **並列の**  のディレクティブでは**OMP\_SCHEDULE** は無視されます。  この環境変数の既定値は実装定義されます。  オプションの設定の場合は正の値である場合 *chunk\_size*。   **静的**  のスケジュールの場合は一定である1 という値とした場合を除き*chunk\_size*。   **静的**  スケジュールには既定のチャンクのサイズはループに適用されるスレッドの数ループの反復空間に設定されます。  
  
 例:  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## cref:  
  
-   **For** のディレクティブはページの 11. [セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) が表示されます。  
  
-   **並列の**  のディレクティブはページの 16 [セクション 2.5.1](../Topic/2.5.1%20parallel%20for%20Construct.md) が表示されます。