---
title: "推論による依存ファイル | Microsoft Docs"
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
helpviewer_keywords: 
  - "依存, 推論による"
  - "推論による依存ファイル (NMAKE の)"
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 推論による依存ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

推論による依存ファイルは、推論規則から派生し、明示的な依存ファイルの前に評価されます。  推論による依存ファイルがターゲットと比べて古い場合は、その依存関係のコマンド ブロックが呼び出されます。  推論による依存ファイルが存在しないか、またはそれ自身の依存ファイルと比べて古い場合、NMAKE はまず推論による依存ファイルを更新します。  推論による依存ファイルの詳細については、「[推論規則](../build/inference-rules.md)」を参照してください。  
  
## 参照  
 [依存ファイル](../build/dependents.md)