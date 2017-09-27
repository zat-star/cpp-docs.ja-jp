---
title: "関係演算子: &lt;、 &gt;、 &lt;=、および&gt;= |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- <
- '>'
dev_langs:
- C++
helpviewer_keywords:
- '> operator'
- less than operator
- relational operators, syntax
- '>= operator'
- greater than or equal to operators
- greater than operators
- < operator
- less than or equal to operator
- <= operator
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 56eead68e733a3950915af2227cbeb0a1bfabbd4
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="relational-operators-lt-gt-lt-and-gt"></a>関係演算子: &lt;、 &gt;、 &lt;=、および&gt;=
## <a name="syntax"></a>構文  
  
```  
expression < expression  
expression > expression  
expression <= expression  
expression >= expression  
```  
  
## <a name="remarks"></a>コメント  
 二項関係演算子は次のリレーションシップを判断します。  
  
-   小さい (**\<**)  
  
-   大きい (**>**)  
  
-   以下を (**\<=**)  
  
-   大きいまたは等しい (**>=**)  
  
 関係演算子の結合規則は、左から右方向です。 関係演算子のオペランドは、両方とも数値型またはポインター型である必要があります。 これらは型 `bool` の値を生成します。 戻り値は**false** (0) 場合は、式のリレーションシップが false です。 それ以外の場合、返される値は**true** (1)。  
  
## <a name="example"></a>例  
  
```  
// expre_Relational_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << "The true expression 3 > 2 yields: "  
         << (3 > 2) << endl  
         << "The false expression 20 < 10 yields: "  
         << (20 < 10) << endl;  
}  
```  
  
 上記の例の式は、ために、かっこで囲む必要があります、ストリーム挿入演算子 (**<<**) は関係演算子よりも優先順位が高いです。 したがって、かっこがない最初の式は次のように評価されます。  
  
```  
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");  
```  
  
 通常の算術変換は、「[標準変換](standard-conversions.md)数値型オペランドに適用されます。  
  
## <a name="comparing-pointers"></a>ポインターの比較  
 同じ型のオブジェクトへの 2 つのポインターを比較する場合、結果はプログラムのアドレス空間で指すオブジェクトの位置によって決まります。 ポインターは、0 または void * 型のポインターに評価される定数式と比較することもできます。 ポインターの比較はに対して行われたかどうか、ポインター型の void \*、他のポインターは暗黙的に void 型への変換\*です。 次に、比較が行われます。  
  
 次の場合を除いて、異なる型の 2 つのポインターを比較することはできません。  
  
-   1 つの型が、他の型の派生クラス型である。  
  
-   ポインターのうち少なくとも 1 つが void * 型に明示的に変換 (キャスト) される  (他のポインターは暗黙的に void 型への変換\*を変換します)。  
  
 同じオブジェクトを指す同じ型の 2 つのポインターは、等しい結果になることが保証されています。 オブジェクトの非静的メンバーへの 2 つのポインターを比較する場合、次の規則が適用されます。  
  
-   クラス型が共用体型でない場合、および 2 つのメンバーがによって分離されていない場合、*アクセス指定子*、パブリック、プロテクト、またはプライベートに宣言されたメンバーへのポインター最後はよりも大きいと宣言されたメンバーへのポインター先ほどの。  
  
-   2 つのメンバーで隔てられている場合、*アクセス指定子*結果は未定義です。  
  
-   クラス型が共用体である場合は、その共用体の異なるデータ メンバーへのポインターが等しいと見なされます。  
  
 2 個のポインターが、同じ配列の要素、または配列の末尾の次の位置の要素をポイントしている場合、より上位の添字を持つオブジェクトへのポインターが高く評価されます。 ポインターの比較は、ポインターが同じ配列のオブジェクトまたは配列の末尾の次の位置を参照している場合にのみ、有効であると保証されます。  
  
## <a name="see-also"></a>関連項目  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 関係演算子と等値演算子](../c-language/c-relational-and-equality-operators.md)
