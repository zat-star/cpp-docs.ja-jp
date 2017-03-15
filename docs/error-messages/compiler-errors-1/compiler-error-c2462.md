---
title: "コンパイラ エラー C2462 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2462"
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 型を 'new' 演算子のオペランド フィールド内で定義することはできません。  
  
 型定義を `new` 演算子のオペランド フィールドで行うことはできません。  型定義は別のステートメント内に置いてください。  
  
 次の例では警告 C2462 が生成されます。  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```