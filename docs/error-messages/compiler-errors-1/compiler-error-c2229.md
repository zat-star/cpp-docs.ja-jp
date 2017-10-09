---
title: "コンパイラ エラー C2229 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2229
dev_langs:
- C++
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c54e3affb39cb396df1caaafe6450d5c6ac80f6e
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2229"></a>コンパイラ エラー C2229
'identifier' の型が無効なサイズ 0 の配列  
  
 構造体またはビット フィールドのメンバーには、最後のメンバーではない、サイズが 0 の配列が含まれています。  
  
 サイズ 0 の配列は、構造体の最後のメンバーとして持つことができます、ため構造体を割り当てるときのサイズを指定する必要があります。  
  
 サイズ 0 の配列が構造体の最後のメンバーでない場合、コンパイラはその他のフィールドのオフセットを計算できません。  
  
 次の例では、C2229 が生成されます。  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```
