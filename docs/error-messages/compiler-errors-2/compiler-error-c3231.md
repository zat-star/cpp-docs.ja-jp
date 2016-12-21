---
title: "コンパイラ エラー C3231 | Microsoft Docs"
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
  - "C3231"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3231"
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3231
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : テンプレート型引数はジェネリック型パラメーターを使用することはできません  
  
 テンプレートはコンパイル時にインスタンス化されますが、ジェネリックは実行時にインスタンス化されます。  したがって、ジェネリック型が認識される実行時にはテンプレートをインスタンス化できないため、テンプレートを呼び出すジェネリック コードは生成できません。  
  
 次の例では警告 C3231 が生成されます。  
  
```  
// C3231.cpp  
// compile with: /clr /LD  
template <class T> class A;  
  
generic <class T>  
ref class C {  
   void f() {  
      A<T> a;   // C3231  
   }  
};  
```