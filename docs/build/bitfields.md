---
title: "ビット フィールド | Microsoft Docs"
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
helpviewer_keywords: 
  - "bitfield"
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ビット フィールド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

構造体のビット フィールドは 64 ビットに制限されており、signed int、unsigned int、int64、unsigned int64 のいずれかの型を指定できます。  型の境界を超えるビット フィールドは、ビットをスキップして次に型を配置する位置に配置されます。  たとえば、整数ビット フィールドは、32 ビット境界を超えることはありません。  
  
## 参照  
 [型とストレージ](../build/types-and-storage.md)