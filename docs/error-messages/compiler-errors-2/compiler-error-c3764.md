---
title: "コンパイラ エラー C3764 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3764"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3764"
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3764
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override\_function': 基本クラス メソッド 'base\_class\_function' をオーバーライドすることはできません  
  
 不正な形式のオーバーライドが検出されました。  たとえば、基本クラス関数が `virtual` ではありませんでした。  詳細については、「[override](../../windows/override-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3764 エラーが生成されます。  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## 使用例  
 C3764 は、基本クラス メソッドが明示的で、かつ名前付きでオーバーライドされている場合にも発生することがあります。  次の例では C3764 エラーが生成されます。  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```