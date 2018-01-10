---
title: "コンパイラ エラー C2387 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2387
dev_langs: C++
helpviewer_keywords: C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d10497a014213623e32f2e77bbd48d4f78c9bf33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2387"></a>コンパイラ エラー C2387
'type': あいまいな基底クラス  
  
 コンパイラ解決できませんでした明確に関数呼び出しに 1 つ以上の基底クラス関数が存在するためです。  
  
 このエラーを解決するから削除する基本クラスのいずれかの継承、か、関数呼び出しを明示的に修飾します。  
  
 次の例では、C2387 が生成されます。  
  
```  
// C2387.cpp  
namespace N1 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
namespace N2 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
struct D : N1::B, N2::B {  
   virtual void f() {  
      B::f();   // C2387  
      // try the following line instead  
      // N1::B::f();  
   }  
};  
  
int main() {  
   D aD;  
   aD.f();  
}  
```