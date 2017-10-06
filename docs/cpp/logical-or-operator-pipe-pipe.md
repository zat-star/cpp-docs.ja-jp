---
title: "論理 OR 演算子: | ||Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '||'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
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
ms.openlocfilehash: 1784a3f0e7d069f7f7e2976fc7b71ea130d7c34b
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="logical-or-operator-"></a>論理 OR 演算子: ||
## <a name="syntax"></a>構文  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## <a name="remarks"></a>コメント  
 論理 OR 演算子 (`||`) ブール値を返します**true**いずれかまたは両方のオペランドがある場合**true**し、返します**false**それ以外の場合。 オペランドは、評価前に `bool` 型に暗黙的に変換され、結果は `bool` 型です。 論理 OR の結合規則は左から右です。  
  
 論理 OR 演算子のオペランドが同じ型である必要はありませんが、整数型またはポインター型である必要があります。 オペランドは一般に関係式または等価式です。  
  
 最初のオペランドが完全に評価され、すべての副作用が完了した後で、論理 OR 式の評価が続行されます。  
  
 2 番目のオペランドは、最初のオペランドが false (0) と評価された場合にのみ、評価されます。 これにより、論理 OR 式が true の場合に 2 番目のオペランドの無駄な評価が行われないようになっています。  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 上の例では、`x` が `w`、`y`、または `z` と等しい場合、`printf` 関数の 2 番目の引数が true に評価され、値 1 が出力されます。 それ以外の場合は、false と評価され、値 0 が出力されます。 条件の 1 つが true と評価されると、直ちに評価が終了します。  
  
## <a name="operator-keyword-for-124124"></a>演算子キーワード &#124; & #124 です。  
 **または**演算子に相当するテキストは、`||`です。 アクセスする方法を次の 2 つが、**または**をプログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、コンパイル時に、または、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語の拡張機能を無効にする) コンパイラ オプション。  
  
## <a name="example"></a>例  
  
```  
// expre_Logical_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical OR  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b || b > c yields "  
         << (a < b || b > c) << endl  
         << "The false expression "  
         << "a > b || b > c yields "  
         << (a > b || b > c) << endl;  
}  
```  
  
## <a name="see-also"></a>関連項目  
[C++ 組み込み演算子の優先順位と結合規則](cpp-built-in-operators-precedence-and-associativity.md) [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 論理演算子](../c-language/c-logical-operators.md)
