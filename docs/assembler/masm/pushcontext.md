---
title: "PUSHCONTEXT | Microsoft Docs"
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
  - "PUSHCONTEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PUSHCONTEXT directive"
ms.assetid: 18e528ee-df6c-4ce6-8823-b35b40f757fd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# PUSHCONTEXT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在の一部またはすべてを保存します `context`: セグメント レジスタは基数の値リストおよびクロス リファレンスのフラグまたはプロセッサとコプロセッサの値であると見なします。  `context` は  **想定しています** `RADIX` **一覧 CPU**または  **すべて**  のいずれかになります。  
  
## 構文  
  
```  
  
PUSHCONTEXT context  
```  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)