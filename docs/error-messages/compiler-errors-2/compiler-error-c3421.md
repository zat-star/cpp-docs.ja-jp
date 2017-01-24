---
title: "コンパイラ エラー C3421 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3421"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3421"
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3421
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': このクラスのファイナライザーは、アクセスできないか、または存在しないため、呼び出すことができません  
  
 ファイナライザーは暗黙的にプライベートであるため、それを囲む型の外部から呼び出すことはできません。  
  
 詳細については、「[Visual C\+\+ のデストラクターおよびファイナライザー](../../misc/destructors-and-finalizers-in-visual-cpp.md)」を参照してください。  
  
## 使用例  
 次の例では C3421 が生成されます。  
  
```  
// C3421.cpp // compile with: /clr ref class A {}; ref class B { !B() {} public: ~B() {} }; int main() { A a; a.!A();   // C3421 B b; b.!B();   // C3421 }  
```