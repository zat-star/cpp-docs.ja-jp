---
title: "コンパイラの警告 (レベル 4) C4487 | Microsoft Docs"
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
  - "C4487"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4487"
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4487
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'derived\_class\_function' : 継承された仮想でないメソッド 'base\_class\_function' と一致しますが、'new' に明示的に設定されていません  
  
 派生クラスの関数のシグネチャが非仮想基本クラスの関数のシグネチャと同じです。  C4487 は、派生クラスの関数は基本クラスの関数をオーバーライドしないことを示します。  この警告を解決するには、派生クラスの関数を `new` として明示的にマークします。  
  
 詳細については、「[new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C4487 エラーが生成されます。  
  
```  
// C4487.cpp  
// compile with: /W4 /clr  
using namespace System;  
public ref struct B {  
   void f() { Console::WriteLine("in B::f"); }  
   void g() { Console::WriteLine("in B::g"); }  
};  
  
public ref struct D : B {  
   void f() { Console::WriteLine("in D::f"); }   // C4487  
   void g() new { Console::WriteLine("in D::g"); }   // OK  
};  
  
int main() {  
   B ^ a = gcnew D;  
   // will call base class functions  
   a->f();  
   a->g();  
}  
```