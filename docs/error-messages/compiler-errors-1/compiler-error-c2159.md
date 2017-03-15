---
title: "コンパイラ エラー C2159 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2159"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2159"
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2159
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2 つ以上のストレージ クラスが指定されています。  
  
 宣言に複数のストレージ クラスが含まれています。  
  
 次の例では C2159 が生成されます。  
  
```  
// C2159.cpp // compile with: /c static int i;   // OK extern static int i;   // C2159  
```