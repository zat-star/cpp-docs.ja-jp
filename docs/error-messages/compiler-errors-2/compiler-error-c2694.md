---
title: "コンパイラ エラー C2694 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2694"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2694"
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2694
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override': 仮想関数のオーバーライドは、基本クラス仮想メンバー関数 'base' よりも制限が少ない例外指定を含んでいます。  
  
 仮想関数がオーバーライドされましたが、[\/Za](../../build/reference/za-ze-disable-language-extensions.md) では、オーバーライドしている関数の方が[例外指定](../../cpp/exception-specifications-throw-cpp.md)の制限が少なくなっていました。  
  
 次の例では警告 C2694 が生成されます。  
  
```  
// C2694.cpp  
// compile with: /Za /c  
class MyBase {  
public:  
   virtual void f(void) throw(int) {  
   }  
};  
  
class Derived : public MyBase {  
public:  
   void f(void) throw(...) {}   // C2694  
   void f2(void) throw(int) {}   // OK  
};  
```