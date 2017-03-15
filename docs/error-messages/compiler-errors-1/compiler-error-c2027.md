---
title: "コンパイラ エラー C2027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2027"
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

認識できない型 'type' が使われています。  
  
 型は定義せずに使うことはできません。  このエラーを解決するには、型を完全に定義してから参照してください。  
  
## 使用例  
 次の例では C2027 エラーが生成されます。  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## 使用例  
 宣言されているが未定義の型へのポインターを宣言することはできます。しかし、Visual C\+\+ では、未定義の型への参照は許可されません。  
  
 次の例では C2027 エラーが生成されます。  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```