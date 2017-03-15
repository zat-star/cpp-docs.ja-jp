---
title: "ML Nonfatal Error A2133 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2133"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2133"
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2133
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**INVOKE が上書きされるレジスタ値**  
  
 引数として登録はプロシージャに渡されましたが他の引数を渡すに [呼び出し](../../assembler/masm/invoke.md) によって生成されたコードはレジスタの内容を破棄します。  
  
 アセンブラーでAL Ax はああEAXDXDLDH および EDX レジスタ データ変換を実行するために使用されることがあります。  
  
 別の登録を使用します。  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)