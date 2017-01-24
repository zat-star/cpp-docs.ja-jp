---
title: "2.8 Directive Binding | Microsoft Docs"
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
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.8 Directive Binding
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ディレクティブの動的バインディングは次の規則に従う必要があります :  
  
-   が 1 の場合**For セクション  シングル  マスター**  と  **バリア**  のディレクティブは動的で囲みます  **並列**  にそのディレクティブ内の **If** の各句の値に関係なくバインドします。  並列領域が現在実行されていない場合ディレクティブはマスター スレッドだけで構成されたチームによって実装されます。  
  
-   **順序あり**  のディレクティブは動的で囲みます **For** にバインドします。  
  
-   **アトミック**  のディレクティブはすべてのスレッドの  **アトミック**  のディレクティブに対して排他的に現在のチームが適用されます。  
  
-   **重大**  のディレクティブはすべてのスレッドの  **重大**  のディレクティブに対して排他的に現在のチームが適用されます。  
  
-   ディレクティブは最も近い動的で囲みます  **並列**  以外のすべてのディレクティブはバインドすることはできません。