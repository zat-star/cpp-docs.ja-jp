---
title: "コンパイラ エラー C3499 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3499
dev_langs:
- C++
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 141d21be57d1aaa6957bbb9fe2d1ac5c0139076a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3499"></a>コンパイラ エラー C3499
void の戻り値の型を持つように指定されているラムダは、値を返すことができません  
  
 コンパイラでは、戻り値の型として `void` を指定するラムダ式によって値が返される場合、またはラムダ式に複数のステートメントが含まれており、値を返すものの、その戻り値の型が指定されていない場合に、このエラーが生成されます。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   ラムダ式から値を返さないようにする  
  
-   ラムダ式の戻り値の型を指定する  
  
-   ラムダ式の本体を構成するステートメントを結合して、単一のステートメントにする  
  
## <a name="example"></a>例  
 次の例では、ラムダ式の本体に複数のステートメントが含まれており、値を返すものの、ラムダ式で戻り値の型が指定されていないため、C3499 が生成されます。  
  
```  
// C3499a.cpp  
  
int main()  
{  
   [](int x) { int n = x * 2; return n; } (5); // C3499  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C3499 について考えられる 2 つの解決策を示します。 最初の解決策では、ラムダ式の戻り値の型を指定します。 2 番目の解決策では、ラムダ式の本体を構成するステートメントを結合して、単一のステートメントにします。  
  
```  
// C3499b.cpp  
  
int main()  
{  
   // Possible resolution 1:   
   // Provide the return type of the lambda expression.  
   [](int x) -> int { int n = x * 2; return n; } (5);  
  
   // Possible resolution 2:   
   // Combine the statements that make up the body of   
   // the lambda expression into a single statement.  
   [](int x) { return x * 2; } (5);  
}  
```  
  
## <a name="see-also"></a>参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)