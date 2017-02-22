---
title: "コンパイラ エラー C3731 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3731"
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

イベント 'function1' とハンドラー 'function2' に互換性がありません。イベントソースとイベント ハンドラーが同じ型でなければなりません。  
  
 イベント ソースとイベント レシーバーは同じ型 \(たとえば `native` と `com` 型\) が必要です。  このエラーを解決するには、イベント ソースとイベント ハンドラーの型を同じにします。  
  
 次の例では警告 C3731 が生成されます。  
  
```  
// C3731.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
[event_source(native)]  
struct A {  
   __event void MyEvent();  
};  
  
[event_receiver(managed)]  
// try the following line instead  
// [event_receiver(native)]  
struct B {  
   void func();  
   B(A a) {  
      __hook(&A::MyEvent, &a, &B::func);   // C3731  
   }  
};  
  
int main() {  
}  
```