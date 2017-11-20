---
title: "コンパイラ エラー C3731 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3731
dev_langs: C++
helpviewer_keywords: C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ac117c6c2020607d5b2d15b0229eaa045a22ec99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3731"></a>コンパイラ エラー C3731
互換性のないイベント 'function1' とハンドラー 'function2';イベント ソースとイベント ハンドラーが同じ型にする必要があります。  
  
 イベント ソースとイベント レシーバーは、同じ型を持つ必要があります (たとえば`native`と`com`型)。 このエラーを解決するには、イベント ソースとイベント ハンドラーの一致の種類を作成します。  
  
 次の例では、C3731 が生成されます。  
  
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