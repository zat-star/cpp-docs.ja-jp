---
title: "致命的なエラー C1046 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1046"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1046"
ms.assetid: 822ec5f5-b0b0-4711-99e1-fc237b619af6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1046
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの制限 : 構造体の入れ子のレベルが深すぎます。  
  
 構造体、共用体、またはクラスが入れ子レベルの制限 15 を超えています。  定義を書き直して、入れ子レベルを減らしてください。  入れ子になった 1 つ以上の構造体を `typedef`  を使用して定義すると、構造体、共用体、またはクラスを 2 つ以上の部分に分割できます。