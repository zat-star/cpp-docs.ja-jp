---
title: "コンパイラ エラー C3485 | Microsoft Docs"
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
  - "C3485"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3485"
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3485
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ラムダ定義に cv 修飾子は使用できません  
  
 ラムダ式の定義の一部として `const` 修飾子または `volatile` 修飾子を使用することはできません。  
  
### このエラーを解決するには  
  
-   ラムダ式の定義から `const` 修飾子または `volatile` 修飾子を削除します。  
  
## 使用例  
 次の例では、ラムダ式の定義の一部として `const` 修飾子を使用しているため、C3485 が生成されます。  
  
```  
// C3485.cpp int main() { auto x = []() const mutable {}; // C3485 }  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)