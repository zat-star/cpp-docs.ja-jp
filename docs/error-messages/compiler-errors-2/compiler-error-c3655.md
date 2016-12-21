---
title: "コンパイラ エラー C3655 | Microsoft Docs"
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
  - "C3655"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3655"
ms.assetid: 724919ab-2915-4b61-8794-44648e162d62
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3655
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : 関数は既に明示的にオーバーライドされています  
  
 関数を明示的にオーバーライドできるのは一度だけです。  詳細については、「[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3655 が生成されます。  
  
```  
// C3655.cpp  
// compile with: /clr /c  
public ref struct B {  
   virtual void f();  
   virtual void g();  
};  
  
public ref struct D : B {  
   virtual void f() new sealed = B::f;  
   virtual void g() new sealed = B::f;   // C3655  
   // try the following line instead  
   // virtual void g() new sealed = B::g;  
};  
```