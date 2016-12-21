---
title: "コンパイラの警告 (レベル 1) C4803 | Microsoft Docs"
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
  - "C4803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4803"
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method' : raise メソッドはイベントのストレージ クラスとは異なるストレージ クラスを持っています。'event'  
  
 イベントのメソッドには、イベント宣言と同じストレージ クラスが必要です。  コンパイラは、ストレージ クラスが同じになるようにイベントのメソッドを調整します。  
  
 この警告は、インターフェイスからイベントを実装するクラスを使用すると生成される場合があります。  **raise** メソッドは、インターフェイス内のイベントに対しては暗黙に生成されません。  そのインターフェイスをクラスで実装すると、**raise** メソッドが暗黙に生成されます。**raise** メソッドは仮想メソッドではないため警告が生成されます。  
  
 警告をオフにする方法については、[warning](../../preprocessor/warning.md) プラグマに関するトピックを参照してください。  
  
## 使用例  
 C4803 は **\/clr** の使用で生成されることがあります。  イベントの使い方の詳細については、「[event](../../windows/event-cpp-component-extensions.md)」を参照してください。  
  
 次の例では C4803 エラーが生成されます。  
  
```  
// C4803.cpp  
// compile with: /clr /W1  
using namespace System;  
  
public delegate void Del();  
  
ref struct E {  
   Del ^ _pd1;  
   event Del ^ E1 {  
      void add (Del ^ pd1) {  
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));  
      }  
  
      void remove(Del^ pd1) {  
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));  
      }  
  
      virtual void raise() {   // C4803 warning (remove virtual)  
         if (_pd1)  
            _pd1();  
      }  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E ^ ep = gcnew E;  
   ep->E1 += gcnew Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= gcnew Del(ep, &E::func);  
   ep->E1();  
}  
```  
  
## 使用例  
 C4803 は **\/clr:oldSyntax** の使用で生成されることがあります。  次の例では C4803 エラーが生成されます。  
  
```  
// C4803_b.cpp  
// compile with: /clr:oldSyntax /W1  
using namespace System;  
  
public __delegate void Del();  
  
__gc struct E {  
   Del* _pd1;  
   virtual __event void add_E1(Del* pd1) {  
      _pd1 = dynamic_cast<Del*> (Delegate::Combine(_pd1, pd1));  
   }  
  
   virtual __event void remove_E1(Del* pd1) {  
      _pd1 = dynamic_cast<Del*> (Delegate::Remove(_pd1, pd1));  
   }  
  
   __event void raise_E1 () {   // C4803, add virtual  
      if (_pd1)  
         _pd1->Invoke();  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E* ep = new E;  
   ep->E1 += new Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= new Del(ep, &E::func);  
   ep->E1();  
}  
```