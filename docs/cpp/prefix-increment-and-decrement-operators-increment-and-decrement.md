---
title: "前置インクリメント演算子と前置デクリメント演算子: + + および--|Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs:
- C++
helpviewer_keywords:
- increment operators [C++], syntax
- ++ operator [C++], prefix increment operators
- operators [C++], decrement
- -- operator [C++], prefix decrement operators [C++]
- operators [C++], increment
- decrement operators [C++], syntax
- decrement operators [C++]
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 22844a2bca61b81dc5cf7c2fc4fffa45a2783078
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="prefix-increment-and-decrement-operators--and---"></a>前置インクリメント演算子と前置デクリメント演算子: ++ および --
## <a name="syntax"></a>構文  
  
```  
++ unary-expression  
-- unary-expression  
```  
  
## <a name="remarks"></a>コメント  
 前置インクリメント演算子 (`++`) は、オペランドに 1 を追加します。このインクリメントされた値が式の結果になります。 オペランドがない型の左辺値にする必要があります**const**です。 結果は、オペランドと同じ型の左辺値です。  
  
 前置デクリメント演算子 (**--**) が、オペランドから 1 が減算され、結果はこのデクリメントされた値は、前置インクリメント演算子と似ています。  

 **Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 型のインクリメントまたはデクリメント演算子のオペランドができない可能性があります`bool`です。
  
 前置および後置インクリメントおよびデクリメント演算子は、オペランドに影響します。 これらの主要な違いは、式の評価でインクリメントまたはデクリメントが発生する順序です。 (詳細については、次を参照してください[後置インクリメント演算子と前置デクリメント演算子](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)。)。前置形式では、値が式評価で使用される前にインクリメントまたはデクリメントが発生するため、式の値はオペランドの値と異なります。 後置形式では、値が式評価で使用された後にインクリメントまたはデクリメントが発生するため、式の値はオペランドの値と同じになります。 たとえば、次のプログラムでは、"`++i = 6`" と出力されます。  
  
```  
// expre_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int i = 5;  
   cout << "++i = " << ++i << endl;  
}  
```  
  
 整数または浮動小数点型のオペランドは、整数値 1 ずつインクリメントまたはデクリメントされます。 結果の型は、オペランドの型と同じです。 ポインター型のオペランドは、アドレス指定するオブジェクトのサイズだけインクリメントまたはデクリメントされます。 インクリメントされたポインターは、次のオブジェクトを指します。デクリメントされたポインターは、前のオブジェクトを指します。  
  
 インクリメントおよびデクリメント演算子に副作用があるでインクリメントまたはデクリメント演算子を含む式を使用して、[プリプロセッサ マクロ](../preprocessor/macros-c-cpp.md)望ましくない結果を持つことができます。 次の例について考えます。  
  
```  
// expre_Increment_and_Decrement_Operators2.cpp  
#define max(a,b) ((a)<(b))?(b):(a)  
  
int main()  
{  
   int i = 0, j = 0, k;  
   k = max( ++i, j );  
}  
```  
  
 マクロは次のように展開されます。  
  
```  
k = ((++i)<(j))?(j):(++i);  
```  
  
 `i` が `j` 以上であるか、`j` より 1 少ない場合、2 回インクリメントされます。  
  
> [!NOTE]
>  C++ のインライン関数は、ここで説明したような副作用をなくし、言語でより完全な型チェックを実行できるため、多くの場合、マクロよりも適しています。  
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [前置インクリメント演算子と前置デクリメント演算子](../c-language/prefix-increment-and-decrement-operators.md)
