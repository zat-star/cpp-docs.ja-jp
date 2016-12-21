---
title: "コンパイラ エラー C3671 | Microsoft Docs"
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
  - "C3671"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3671"
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3671
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function\_1' : 関数は 'function\_2' をオーバーライドしません  
  
 明示的なオーバーライド構文を使用する場合に関数がオーバーライドされないときは、コンパイルがエラーを生成します。詳細については、「[Explicit Overrides](../../windows/explicit-overrides-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3671 エラーが生成されます。  
  
```  
// C3671.cpp  
// compile with: /clr /c  
ref struct S {  
   virtual void f();  
};  
  
ref struct S1 : S {  
   virtual void f(int) new sealed = S::f;   // C3671  
   virtual void f() new sealed = S::f;  
};  
```