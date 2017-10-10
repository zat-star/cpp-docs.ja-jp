---
title: "コンパイラ エラー C2804 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2804
dev_langs:
- C++
helpviewer_keywords:
- C2804
ms.assetid: b066e563-cca4-450c-8ba7-3b0d7a89f3ea
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 42669f02fb687c35ee159cb28b852e13281a83f1
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2804"></a>コンパイラ エラー C2804
二項 'operator 演算子' のパラメーターが多すぎます。  
  
 オーバーロードされた二項演算子のメンバー関数が、複数のパラメーターを指定して宣言されています。 型が演算子の外側の型になっている二項演算子メンバー関数の 1 つ目のオペランド パラメーターは、暗黙的に指定されます。  
  
## <a name="example"></a>例  
 次の例では、C2804 を生成し、その修正方法を示しています。  
  
```  
// C2804.cpp  
// compile by using: cl /c /W4 C2804.cpp  
class X {  
public:  
   X& operator+= (const X &left, const X &right);   // C2804  
   X& operator+= (const X &right);   // OK - left operand implicitly *this  
};  
  
int main() {  
   X x, y;  
   x += y;   // equivalent to x.operator+=(y)  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C2804 を生成し、その修正方法を示しています。  
  
```  
// C2804_2.cpp  
// compile with: /clr /c  
ref struct Y {  
   Y^ operator +(Y^ hY, int i);   // C2804  
   static Y^ operator +(Y^ hY, int i);   // OK  
   Y^ operator +(int i);   // OK  
};  
```
