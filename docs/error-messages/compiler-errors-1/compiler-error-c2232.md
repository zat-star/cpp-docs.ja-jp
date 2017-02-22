---
title: "コンパイラ エラー C2232 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2232"
ms.assetid: 76f302b7-30a7-4a81-9a39-b4edde33b54c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'–\>': 左のオペランドが 'class\-key' 型です。'.' を使用してください。  
  
 `->` 演算子の左のオペランドがポインターではありません。 クラス、構造体、または共用体に対しては、ピリオド \(.\)  演算子を使用してください。  
  
 次の例では C2232 が生成されます。  
  
```  
// C2232.c struct X { int member; } x, *px; int main() { x->member = 0;   // C2232, x is not a pointer px->member = 0; x.member = 0; }  
```