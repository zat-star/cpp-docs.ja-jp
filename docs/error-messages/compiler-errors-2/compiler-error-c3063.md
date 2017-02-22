---
title: "コンパイラ エラー C3063 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3063"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3063"
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3063
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

演算子 '演算子': すべてのオペランドには、同じ列挙型を指定しなければなりません  
  
 列挙子で演算子を使用するときは、両方のオペランドの列挙型が同じであることが必要です。  詳細については、「[演算子と列挙型の使用](../Topic/Operators%20and%20Enumerations.md)」を参照してください。  
  
 次の例では警告 C3063 が生成されます。  
  
```  
// C3063.cpp  
// compile with: /clr  
enum class E { a, b } e, mask;  
int main() {  
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```