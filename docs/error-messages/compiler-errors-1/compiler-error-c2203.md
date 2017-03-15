---
title: "コンパイラ エラー C2203 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2203"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2203"
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2203
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

delete 演算子では配列の一部や特定のメンバーを削除することはできません。  
  
 **\/Za** \(ANSI\) オプションを指定しても、`delete` 演算子は配列全体しか削除できません。配列の一部分や配列の指定したメンバーは削除できません。  
  
 次の例では警告 C2203 が生成されます。  
  
```  
// C2203.cpp  
// compile with: /Za  
int main() {  
   int *ar = new int[10];  
   delete [4] ar;   // C2203  
   // try the following line instead  
   // delete [] ar;  
}  
```