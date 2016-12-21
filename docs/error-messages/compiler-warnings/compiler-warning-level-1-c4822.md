---
title: "コンパイラの警告 (レベル 1) C4822 | Microsoft Docs"
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
  - "C4822"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4822"
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4822
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': ローカル クラスのメンバー関数は本体がありません  
  
 ローカル クラス メンバー関数が宣言されましたが、クラスに定義されていません。 ローカル クラス メンバー関数を使用するには、その関数をクラスに定義する必要があります。 クラスで宣言する関数をクラス外に定義することはできません。  
  
 ローカル クラス メンバー関数をクラス外に定義すると、エラーになります。  
  
 次の例では C4822 が生成されます。  
  
```  
// C4822.cpp // compile with: /W1 int main() { struct C { void func1(int);   // C4822 // try the following line instead // void func1(int){} }; }  
```