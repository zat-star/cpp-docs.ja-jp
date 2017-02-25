---
title: "コンパイラ エラー C2807 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2807"
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2807
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

後置形式の 'operator operator' に対する第 2 パラメーターは、int 型と宣言しなければなりません。  
  
 後置演算子の 2 番目のパラメーターの型が間違っています。  
  
 次の例では警告 C2807 が生成されます。  
  
```  
// C2807.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( X );   // C2807 nonvoid parameter  
   X operator++ ( int );   // OK, int parameter  
};  
```