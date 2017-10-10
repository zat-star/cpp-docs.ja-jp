---
title: "コンパイラ エラー C2698 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 654367e882b16c18cc4bd58c339d61c653dc68e9
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2698"></a>コンパイラ エラー C2698
using 宣言の '1' の宣言と共存できません既存 using 宣言の' 2' の宣言。  
  
 作成したら、[宣言を使用して](../../cpp/using-declaration.md)データ メンバーを使用しているすべての名前を使用するものと同じスコープ内の宣言は使用できません、のみの関数をオーバー ロードすることができます。  
  
 次の例では、C2698 が生成されます。  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```
