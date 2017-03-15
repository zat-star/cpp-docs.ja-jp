---
title: "コンパイラ エラー C3736 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3736"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3736"
ms.assetid: 579b773c-41e7-40ea-8382-2e3ce2667f4c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3736
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event' : メソッド、またマネージ イベントの場合はデータ メンバーでなければなりません。  
  
 ネイティブ イベントと COM イベントはメソッドにする必要があります。.NET イベントは、データ メンバーにすることもできます。  
  
 次の例では警告 C3736 が生成されます。  
  
```  
// C3736.cpp  
struct A {  
   __event int e();  
};  
  
struct B {  
   int f;   // C3736  
   // The following line resolves the error.  
   // int f();  
   B(A* a) {  
      __hook(&A::e, a, &B::f);  
   }  
};  
  
int main() {  
}  
```