---
title: "A.6   Using the lastprivate Clause | Microsoft Docs"
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
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.6   Using the lastprivate Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

正しい実装はループの最後の反復が変数に割り当てる値によって異なります。  このようなプログラムは `lastprivate` の句 \(ページの 27[セクション 2.7.2.3](../Topic/2.7.2.3%20lastprivate.md)\) に引数チェックなどのループが順次実行時に変数の値が同じになるように変数をすべて記述する必要があります。  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 前の例では並列領域のエッジ `i` 値はシーケンスの場合と同様に`n – 1` になります。