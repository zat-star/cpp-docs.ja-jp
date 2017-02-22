---
title: "コンパイラ エラー C3189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3189"
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

「typeidtype の\<抽象宣言子\>': この構文は、使用する代わり::typeid でサポートされていません。  
  
 旧式の [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) が使用されています。新しい形式を使用してください。  
  
 次の例では警告 C3189 が生成されます。  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```