---
title: "コンパイラ エラー C2352 | Microsoft Docs"
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
  - "C2352"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2352"
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2352
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::function' : 静的でないメンバー関数の呼び出しが正しくありません  
  
 `static` メンバー関数は、静的でないメンバー関数を呼び出しました。  または、静的でないメンバー関数がクラスの外部から静的関数として呼び出されました。  
  
 次の例では、C2352 を生成し、その修正方法を示しています。  
  
```  
// C2352.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1();  
   void func2();  
   static void func3() {  
      func2();   // C2352 calls nonstatic func2  
      func1();   // OK calls static func1  
   }  
};  
```  
  
 次の例では、C2352 を生成し、その修正方法を示しています。  
  
```  
// C2352b.cpp  
class MyClass {  
public:  
   void MyFunc() {}  
   static void MyFunc2() {}  
};  
  
int main() {  
   MyClass::MyFunc();   // C2352  
   MyClass::MyFunc2();   // OK  
}  
```