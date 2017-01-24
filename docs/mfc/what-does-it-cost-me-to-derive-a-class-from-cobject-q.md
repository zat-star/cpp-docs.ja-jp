---
title: "CObject からクラスを派生するときのオーバーヘッド | Microsoft Docs"
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
  - "CObject クラス, オーバーヘッド (派生クラスの)"
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObject からクラスを派生するときのオーバーヘッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CObject](../Topic/CObject%20Class.md) クラスからの派生のオーバーヘッドはごくわずかです。  派生クラスは、4 種類の仮想関数と [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) 単一のオブジェクトだけを継承します。  
  
## 参照  
 [CObject クラス : Q & A 集](../mfc/cobject-class-frequently-asked-questions.md)