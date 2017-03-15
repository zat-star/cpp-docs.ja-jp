---
title: "コンパイラ エラー C2675 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2675"
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラ エラー C2675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

単項演算子 'operator' : 'type' は、この演算子または定義済の演算子に適切な型への変換の定義を行いません。  
  
 C2675 は、単項演算子を使用するときに、この演算子または定義済みの演算子に適切な型への変換を型が定義しない場合にも発生します。  この演算子を使うには、型を指定してこの演算子をオーバーロードするか、この演算子が定義された型への変換を定義する必要があります。  
  
## 使用例  
 次の例では C2675 エラーが生成されます。  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```