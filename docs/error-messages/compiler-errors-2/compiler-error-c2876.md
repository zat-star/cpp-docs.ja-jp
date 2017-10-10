---
title: "コンパイラ エラー C2876 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2876
dev_langs:
- C++
helpviewer_keywords:
- C2876
ms.assetid: 8b674bf1-f9f4-4a8e-8127-e884c1d1708f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 84b5609dab6e8f12c5545c2e5c8d64a173cd41ec
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2876"></a>コンパイラ エラー C2876
'class::symbol': すべてのオーバー ロードがアクセスできます。  
  
 基本クラスの関数のオーバー ロードされたすべてのフォームを派生クラスにアクセスできることがあります。  
  
 次の例では、C2876 が生成されます。  
  
```  
// C2876.cpp  
// compile with: /c  
class A {  
public:     
   double a(double);  
private:  
   int a(int);  
};  
  
class B : public A {  
   using A::a;   // C2876 one overload is private in base class  
};  
```
