---
title: "コンパイラ エラー C2387 | Microsoft Docs"
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
  - "C2387"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2387"
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2387
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : あいまいな基本クラスです  
  
 関数が複数の基本クラス内にあるため、関数呼び出しを明確に解決できませんでした。  
  
 このエラーを解決するには、基本クラスの 1 つを継承から削除するか、関数呼び出しを明示的に修飾します。  
  
 次の例では警告 C2387 が生成されます。  
  
```  
// C2387.cpp  
namespace N1 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
namespace N2 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
struct D : N1::B, N2::B {  
   virtual void f() {  
      B::f();   // C2387  
      // try the following line instead  
      // N1::B::f();  
   }  
};  
  
int main() {  
   D aD;  
   aD.f();  
}  
```