---
title: "コンパイラ エラー C2252 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2252"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2252"
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2252
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のスコープでは、テンプレートを明示的にインスタンス化できません。  
  
 テンプレートの明示的なインスタンス化の問題が検出されました。たとえば、関数内でテンプレートを明示的にインスタンス化することはできません。  
  
 次の例では警告 C2252 が生成されます。  
  
```  
// C2252.cpp  
class A {  
public:  
   template <class T>  
   int getit(int i , T * it ) {  
      return i;  
   }  
   template int A::getit<double>(int i, double * it);   // C2252  
   // try the following line instead  
   // template <> int A::getit<double>(int i, double * it);  
  
};  
  
int main() {  
   // cannot explicitly instantiate in function  
   template int A::getit<long>(int i, long * it);   // C2252  
}  
```