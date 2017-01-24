---
title: "コンパイラ エラー C2764 | Microsoft Docs"
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
  - "C2764"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2764"
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2764
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param' : テンプレート パラメーターは部分的特殊化  '特殊化' では使用されないか、または推論できません。  
  
 テンプレート パラメーターは、部分的な特化では使用されません。  これにより、テンプレート パラメーターを推定できないため、部分的な特化を使用できません。  
  
## 使用例  
 次の例では警告 C2764 が生成されます。  
  
```  
// C2764.cpp  
#include <stdio.h>  
template <class T1, class T2>  
struct S  {  
   int m_i;  
};  
  
template <class T1, class T2>  
struct S<int, T2*> {   // C2764  
// try the following line instead  
// struct S<T1(*)(T2), T2*> {  
   char m_c;  
};  
  
int main() {  
   S<int, char> s1;  
   S<void (*)(short), short *> s2;  
   s2.m_c = 10;  
   s1.m_i = s2.m_c;  
   printf_s("%d\n", s1.m_i);  
}  
```