---
title: "コレクションと列挙子のインターフェイスのデザイン上の原則 | Microsoft Docs"
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
  - "コレクション インターフェイス"
  - "列挙子インターフェイス"
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コレクションと列挙子のインターフェイスのデザイン上の原則
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インターフェイスの種類の後ろに異なるデザイン原則があります:  
  
-   コレクションのインターフェイスは **\[アイテム\]** のメソッドによってコレクションの *一つの* 項目への *ランダム アクセスを* 提供しますが、クライアント数が **Count** のプロパティによってコレクションに検出するようについて説明し、通常、クライアントが項目を追加または削除することができます。  
  
-   列挙子インターフェイスは、コレクションの *複数の* 項目への順次アクセスを提供しますが、クライアント数がコレクション \(列挙子が項目を返すことを停止するまで\)、項目を追加または削除する方法を提供しないことを検出できるようには動作しません。  
  
 インターフェイスの各コレクションは型の要素へのアクセスの別の役割を果たします。  
  
## 参照  
 [コレクションと列挙子](../atl/atl-collections-and-enumerators.md)