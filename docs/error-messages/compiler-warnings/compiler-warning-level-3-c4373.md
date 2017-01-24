---
title: "コンパイラの警告 (レベル 3) C4373 | Microsoft Docs"
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
  - "C4373"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4373"
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4373
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'%$S': 仮想関数は '%$pS' をオーバーライドします。前バージョンのコンパイラは、パラメーターの違いが const\/volatile 修飾子に限られる場合はオーバーライドしませんでした。  
  
 アプリケーションには、基底クラスの仮想メソッドをオーバーライドする派生クラスのメソッドが含まれ、オーバーライドする側のメソッドのパラメーターは、[const](../../cpp/const-cpp.md) または [volatile](../../cpp/volatile-cpp.md) 修飾子についてのみ、仮想メソッドのパラメーターと異なります。 つまり、コンパイラでは、基底クラスまたは派生クラスのいずれかにおけるメソッドに、関数参照をバインドする必要があります。  
  
 [!INCLUDE[cpp_orcas_long](../../error-messages/compiler-warnings/includes/cpp_orcas_long_md.md)] より前のバージョンのコンパイラでは、基底クラスのメソッドに関数をバインドした後、警告メッセージを発行します。 それ以降のバージョンのコンパイラでは、`const` または `volatile` の修飾子を無視して、派生クラスのメソッドに関数をバインドした後、警告 `C4373` を発行します。 この後者の動作は、C\+\+ 標準に準拠しています。  
  
## 使用例  
 次のコード例では、警告 C4373 が生成されます。  
  
```  
// c4373.cpp // compile with: /c /W3 #include <stdio.h> struct Base { virtual void f(int i) { printf("base\n"); } }; struct Derived : Base { void f(const int i) {  // C4373 printf("derived\n"); } }; void main() { Derived d; Base* p = &d; p->f(1); }  
```  
  
```Output  
派生  
```