---
title: "コンパイラ エラー C3652 | Microsoft Docs"
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
  - "C3652"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3652"
ms.assetid: 15d68737-177e-41f1-80e0-7c3e2afdf0fc
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3652
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'オーバーライド' : 明示的にオーバーライドする関数は仮想でなければなりません  
  
 明示的にオーバーライドする関数は仮想であることが必要です。  詳細については、「[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3652 が生成されます。  
  
```  
// C3652.cpp  
// compile with: /clr /c  
public interface class I {  
   void f();  
};  
  
public ref struct R : I {  
   void f() = I::f {}   // C3652  
   // try the following line instead  
   // virtual void f() = I::f {}  
};  
```