---
title: "コンパイラ エラー C2289 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2289"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2289"
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2289
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

同じ型の修飾子が 2 度以上使われています。  
  
 型の宣言または定義で、型修飾子 \(`const`、`volatile`、`signed`、または `unsigned`\) が 2 回以上使用されています。ANSI 互換のオプション \(**\/Za**\) を指定している場合はエラーになります。  
  
 次の例では C2286 が生成されます。  
  
```  
// C2289.cpp // compile with: /Za /c volatile volatile int i;   // C2289 volatile int j;   // OK  
```