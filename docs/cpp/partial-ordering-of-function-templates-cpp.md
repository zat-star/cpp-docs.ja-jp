---
title: "関数テンプレート (C++) の部分的な順序付け |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f460497071445cff87308fa9bf6e0d43c6f13a3e
ms.openlocfilehash: 252f80416f581ecc2c126bc44ab22c1b63c50130
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---

# <a name="partial-ordering-of-function-templates-c"></a>関数テンプレートの部分的な順序付け (C++)

関数呼び出しの引数リストと一致する複数の関数テンプレートを使用できます。 C++ では、呼び出す関数を指定するために、関数テンプレートの部分的な順序が定義されています。 順序が部分的なのは、同等に特殊化されていると見なされるテンプレートが存在するためです。

コンパイラは、使用できる最も特殊化されたテンプレート関数を一致候補から選択します。 たとえば、関数テンプレート型を受け取り、 __T__、およびを別の関数テンプレート__T\* __が使用できる、 __T\* __バージョンと呼びます特殊化の詳細、およびジェネリックをお勧めする__T__バージョンでも両方は使用可能な一致、引数がポインター型、されるたびにします。

1 つの関数テンプレート候補がより特殊化されたかどうかを確認するには、次の手順を使用します。

1. T1 および T2 の 2 つの関数テンプレートを考えます。

2. T1 内のパラメーターを架空の一意の型 X に置き換えます。

3. T1 のパラメーター リストで、T2 がそのパラメーター リストの有効なテンプレートであるかどうかを確認します。 暗黙の変換は無視します。

4. T1 と T2 を逆にして、同じ処理を繰り返します。

5. 1 つのテンプレートが他のテンプレートの有効なテンプレート引数リストであっても、その逆が当てはまらない場合、そのテンプレートは他のテンプレートよりも特殊化されていないと見なされます。 両方のテンプレート引数を使用して、以前ステップ フォーム有効な相互しと見なされます、均等に特殊化するし、あいまいな呼び出しの結果しようとするそれらを使用します。

6. 次の規則を使用します。

     1. 特定の型を受け取るテンプレートは、ジェネリック型引数を受け取るテンプレートよりも特殊化されます。

     2. のみをテンプレート__T\* __は 1 つだけ行うよりも特殊化__T__仮定の型、 __X\* __に対して有効な引数には、__T__テンプレート引数が、 __X__に対して有効な引数ではありません、 __T\* __テンプレートの引数。

     3. __const T__はより特殊化__T__ので、 __const X__に対して有効な引数には、 __T__テンプレート引数が、 __X__有効な引数ではありません、 __const T__テンプレートの引数。

     4. __const T\* __はより特殊化__T\*__ので、 __const X\* __に対して有効な引数には、 __T\*__テンプレート引数が、 __X\* __に対して有効な引数ではありません、 __const T\* __テンプレートの引数。

## <a name="example"></a>例

次の例は、標準で指定としては機能します。

```cpp
// partial_ordering_of_function_templates.cpp
// compile with: /EHsc
#include <iostream>

extern "C" int printf(const char*,...);
template <class T> void f(T) {
   printf_s("Less specialized function called\n");
}

template <class T> void f(T*) {
   printf_s("More specialized function called\n");
}

template <class T> void f(const T*) {
   printf_s("Even more specialized function for const T*\n");
}

int main() {
   int i =0;
   const int j = 0;
   int *pi = &i;
   const int *cpi = &j;

   f(i);   // Calls less specialized function.
   f(pi);  // Calls more specialized function.
   f(cpi); // Calls even more specialized function.
   // Without partial ordering, these calls would be ambiguous.
}
```  
  
### <a name="output"></a>出力  
  
```  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## <a name="see-also"></a>関連項目

[関数テンプレート](../cpp/function-templates.md)

