---
title: "コンパイラ エラー C3541 | Microsoft Docs"
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
  - "C3541"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3541"
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3541
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'auto' を含む型に typeid は適用できません  
  
 [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) 演算子に `auto` 指定子が含まれるため、指定された型に適用できません。  
  
## 使用例  
 次の例では、C3541 が発生します。  
  
```  
// C3541.cpp  
// Compile with /Zc:auto  
#include <typeinfo>  
int main() {  
    auto x = 123;  
    typeid(x);    // OK  
    typeid(auto); // C3541  
    return 0;  
}  
```  
  
## 参照  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [\/Zc:auto \(変数の型の推測\)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md)