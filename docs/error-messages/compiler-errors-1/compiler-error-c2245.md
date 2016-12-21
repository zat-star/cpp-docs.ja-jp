---
title: "コンパイラ エラー C2245 | Microsoft Docs"
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
  - "C2245"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2245"
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2245
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

friend と指定された存在しないメンバー関数 'function' \(メンバー関数署名がオーバーロードと一致しません\)  
  
 フレンドとして指定された関数がコンパイラによって検出されませんでした。  
  
 次の例では C2245 が生成されます。  
  
```  
// C2245.cpp // compile with: /c class B { void f(int i); }; class A { int m_i; friend void B::f(char);   // C2245 // try the following line instead // friend void B::f(int); }; void B::f(int i) { A a; a.m_i = 0; }  
```