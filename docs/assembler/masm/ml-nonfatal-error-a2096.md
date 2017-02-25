---
title: "ML Nonfatal Error A2096 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2096"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2096"
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2096
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**セグメントグループまたは期待されるセグメントの登録**  
  
 セグメントまたはグループを指定する必要がありますが検索します。  
  
 発生する以下のいずれかの操作 :  
  
-   セグメント オーバーライド演算子 \(\) で指定された **:** 左のオペランドはセグメント レジスタ \(CS SS DSFSまたは GS\)グループ名セグメント名またはセグメントの式ではありません。  
  
-   [とします。](../../assembler/masm/assume.md) のディレクティブは有効なセグメントのアドレスを持たないセグメント レジスタセグメント レジスタグループまたは  **フラット**  の特別なグループをいます。  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)