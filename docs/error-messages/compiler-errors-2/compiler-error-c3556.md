---
title: "コンパイラ エラー C3556 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3556"
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'expression': 'decltype' の引数が正しくありません  
  
 コンパイラは `decltype(``expression``)` 型指定子への引数である式の型を推測できません。 次のコード例では、`myFunction` がオーバーロードされているため、コンパイラは `myFunction` 引数の型を推定できません。  
  
```  
void myFunction(); void myFunction(int); decltype(myFunction); // C3556  
```