---
title: "OpenMP Data Types | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OpenMP Data Types
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API で使用されるデータ型へのリンクを示します。  
  
 OpenMP 標準の Visual C\+\+ の実装では以下のデータ型が含まれています。  
  
|データ型|Description|  
|----------|-----------------|  
|[omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md)|ロックが使用可能かどうかはスレッドがロックを所有している場合ロックの状態を保持する型。|  
|[omp\_nest\_lock\_t](../Topic/omp_nest_lock_t.md)|ロックに関する次の情報が 1 を保持する型 : ロックはロックおよび入れ子の数を所有するスレッドの ID使用できるかどうか。|  
  
## 参照  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)