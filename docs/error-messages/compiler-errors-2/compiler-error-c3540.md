---
title: "コンパイラ エラー C3540 | Microsoft Docs"
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
  - "C3540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3540"
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 'auto' を含む型に sizeof は適用できません  
  
 [sizeof](../../cpp/sizeof-operator.md) 演算子に `auto` 指定子が含まれるため、指定された型に適用できません。  
  
## 使用例  
 次の例では、C3540 が発生します。  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## 参照  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [\/Zc:auto \(変数の型の推測\)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof 演算子](../../cpp/sizeof-operator.md)