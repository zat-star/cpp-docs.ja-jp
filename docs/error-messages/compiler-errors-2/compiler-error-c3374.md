---
title: "コンパイラ エラー C3374 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3374"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3374"
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3374
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

delegate インスタンスを作成する場合以外に、'関数' のアドレスを指定できません  
  
 delegate インスタンスを作成する以外のコンテキストで、関数のアドレスが取得されました。  
  
 次の例では警告 C3374 が生成されます。  
  
```  
// C3374.cpp  
// compile with: /clr  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      System::Console::WriteLine("in func1 {0}", i);  
   }  
};  
  
int main() {  
   &A::func1;   // C3374  
  
   // OK  
   A ^ a = gcnew A;  
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);  
}  
```  
  
## 参照  
 [方法: デリゲートを定義および使用する](../Topic/How%20to:%20Define%20and%20Use%20Delegates%20\(C++-CLI\).md)