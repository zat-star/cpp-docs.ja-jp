---
title: "コンパイラ エラー C3487 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3487
dev_langs:
- C++
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: eb659f2d7971d1dd2ff27c438839336d4744767e
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3487"></a>コンパイル エラー C3487
'return type': すべての return 式で同じ型を推測する必要があります: 以前は 'return type' でした。  
  
 ラムダでは、1 つの return ステートメントを含む場合を除き、戻り値の型を指定する必要があります。 ラムダに複数の return ステートメントが含まれる場合は、すべて同じ型である必要があります。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   ラムダの後続の戻り値の型を指定します。 ラムダからのすべての戻り値が同じ型であるか、または戻り値の型に暗黙的に変換できることを確認します。  
  
## <a name="example"></a>例  
 次の例では、ラムダの戻り値の型が一致しないため、C3487 が生成されます。  
  
```  
// C3487.cpp  
// Compile by using: cl /c /W4 C3487.cpp  
  
int* test(int* pi) {  
   // To fix the error, uncomment the trailing return type below  
   auto odd_pointer = [=]() /* -> int* */ {  
      if (*pi % 2)   
         return pi;  
      return nullptr; // C3487 - nullptr is not an int* type  
   };  
   return odd_pointer();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
