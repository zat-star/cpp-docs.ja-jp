---
title: "致命的なエラー C1045 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1045"
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 致命的なエラー C1045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの制限 : 外部参照の入れ子のレベルがコンパイラの限界を超えています。  
  
 入れ子になった外部参照がコンパイラの制限を超えています。 入れ子になった外部参照は、`extern` "C\+\+" などの外部リンケージの種類で許可されます。 エラーを解決するには、入れ子になった外部参照の数を減らします。