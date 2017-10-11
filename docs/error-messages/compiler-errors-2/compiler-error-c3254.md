---
title: "コンパイラ エラー C3254 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3254
dev_langs:
- C++
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 104ee89c45d8a1134611535ab6aa9c62f09e139c
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3254"></a>コンパイラ エラー C3254
'明示的なオーバーライド': クラスは、明示的なオーバーライド 'override' が含まれていますが、関数の宣言を格納しているインターフェイスから派生していません  
  
 ときに、[を明示的にオーバーライド](../../cpp/explicit-overrides-cpp.md)メソッド オーバーライドを含むクラス必要があります、直接または間接的に派生、オーバーライドする関数を含む型からです。  
  
 次の例では、C3254 が生成されます。  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```
