---
title: "C 後置インクリメント演算子と後置デクリメント演算子 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "インクリメント演算子, 構文"
  - "スカラー演算子"
  - "型 [C], スカラー"
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 後置インクリメント演算子と後置デクリメント演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

後置インクリメントと後置デクリメントのオペランドは、スカラー型の変更可能な左辺値です。  
  
## 構文  
 *postfix\-expression*:  
 *postfix\-expression*  **\+\+**  
  
 *postfix\-expression*  **––**  
  
 後置インクリメントまたは後置デクリメントの演算結果は、オペランドの値になります。  結果が得られた後で、オペランドの値がインクリメント \(またはデクリメント\) されます。  次のコードは、後置インクリメント演算子を示しています。  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
 この例では、変数 `var` は 0 と比較されてからインクリメントされます。  `var` がインクリメントされる前に正である場合は、次のステートメントが実行されます。  まず、`q` でポイントされるオブジェクトの値が `p` でポイントされるオブジェクトに代入されます。  次に、`q` と `p` がインクリメントされます。  
  
## 参照  
 [後置インクリメント演算子と後置デクリメント演算子: \+\+ および \-\-](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)