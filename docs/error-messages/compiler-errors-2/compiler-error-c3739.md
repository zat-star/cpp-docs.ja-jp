---
title: "コンパイラ エラー C3739 | Microsoft Docs"
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
  - "C3739"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3739"
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3739
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : event\_receiver の 'layout\_dependent' パラメーターが True の場合のみ、構文はサポートされます。  
  
 イベントのインターフェイス全体のフックを試みましたが、[event\_receiver](../../windows/event-receiver.md) 属性の `layout_dependent` が true ではありません。イベントを一度に 1 つずつフックする必要があります。  
  
 次の例では警告 C3739 が生成されます。  
  
```  
// C3739.cpp  
struct A  
{  
   __event void e();  
};  
  
// event_receiver is implied  
// [ event_receiver(layout_dependent=false)]  
  
// use the following line instead  
// [event_receiver(com, layout_dependent=true), coclass ]  
struct B  
{  
   void f();  
   B(A* a)  
   {  
      __hook(A, a, &B::f);   // C3739  
      // use the following line instead to hook a single event  
      // __hook(&A::e, a, &B::f);  
   }  
};  
  
int main()  
{  
}  
```