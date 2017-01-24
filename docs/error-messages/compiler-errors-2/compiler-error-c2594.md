---
title: "コンパイラ エラー C2594 | Microsoft Docs"
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
  - "C2594"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2594"
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2594
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'演算子' : 'type1' から 'type2' への変換はあいまいです。  
  
 *type1* から *type2* への直接変換は他の詳細ではありません。  これは *type1* から *type2*に変換に 2 個の解決策を提案します。  最初に *type1* から *type2*への直接変換を定義する方法で、2 つ目 *type1* から *type2*への変換のシーケンスを指定することです。  
  
 次の例では C2594 エラーが生成されます。  推奨されるエラーの解決方法は、変換のシーケンスです。  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```