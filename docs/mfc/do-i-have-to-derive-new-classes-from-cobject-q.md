---
title: "CObject から新しくクラスを派生する必要性 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject クラス, 使用する時期"
  - "派生クラス, CObject から"
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObject から新しくクラスを派生する必要性
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

いいえをクリックします。  
  
 カスタマイズする機能が必要な場合にシリアル化または動的な creatability などの [CObject](../Topic/CObject%20Class.md) からクラスを派生してください。  多くのデータ クラスはファイルにシリアル化する必要があるため、`CObject`から派生することをお勧めします。  `CObject`から派生したクラスの例については、[Scribble サンプル](../top/visual-cpp-samples.md)を参照してください。  
  
## 参照  
 [CObject クラス : Q & A 集](../mfc/cobject-class-frequently-asked-questions.md)