---
title: "コンパイラ エラー C2271 | Microsoft Docs"
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
  - "C2271"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2271"
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2271
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : new\/delete がメモリ モデル修飾子で宣言されています。  
  
 演算子 \(`new` または `delete`\) がメモリ モデル修飾子で宣言されています。  
  
 次の例では警告 C2271 が生成されます。  
  
```  
// C2271.cpp  
// compile with: /c  
void* operator new(size_t) const {   // C2271  
// try the following line instead  
// void* operator new(size_t) {  
   return 0;  
}  
  
struct X {  
   static void* operator new(size_t) const;   // C2271  
   // try the following line instead  
   // void * X::operator new(size_t) const;   // static member operator new  
};  
```