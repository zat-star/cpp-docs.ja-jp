---
title: "コンパイラ エラー C2553 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2553"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2553"
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2553
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'base\_function': オーバーライドする仮想関数の戻り値の型は 'override\_function' と異なります  
  
 派生クラスの関数が基本クラスの仮想関数をオーバーライドしようとしましたが、派生クラスの関数の戻り値の型が基本クラスの関数の戻り値の型と異なります。オーバーライドする関数のシグネチャは、オーバーライドされる関数のシグネチャと一致する必要があります。  
  
 次の例では警告 C2553 が生成されます。  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```