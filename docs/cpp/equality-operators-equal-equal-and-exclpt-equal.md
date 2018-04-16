---
title: "等値演算子: = =、! = |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- not_eq
- '!='
- ==
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2be0d4cf45bbedc5e799b07962c05f845d5f3efe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="equality-operators--and-"></a>等値演算子: == および !=
## <a name="syntax"></a>構文  
  
```  
expression == expression  
expression != expression  
```  
  
## <a name="remarks"></a>コメント  
 これらの二項等値演算子はそれぞれオペランドを比較し、等しいか、等しくないかを判別します。  
  
 "等しい" (`==`) および "等しくない" (`!=`) の等値演算子は関係演算子より優先順位が下ですが、動作は同じです。 これらの演算子の結果は `bool` 型です。  
  
 演算子の (`==`) を返します**true**場合は、(1) 以外を返しますそれ以外の場合の両方のオペランドが同じ値を持つ**false** (0) です。 Not で等しいかどうかをオペレーター (`!=`) を返します**true**場合、オペランドには、同じ値はありません。 それ以外の場合、返します**false**です。  
  
## <a name="operator-keyword-for-"></a>!= の演算子キーワード  
 `not_eq` 演算子は `!=` の代替表現です。 アクセスする方法を次の 2 つが、`not_eq`をプログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、コンパイル時に、または、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語の拡張機能を無効にする) コンパイラ オプション。  
  
## <a name="example"></a>例  
  
```  
// expre_Equality_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << boolalpha  
         << "The true expression 3 != 2 yields: "  
         << (3 != 2) << endl  
         << "The false expression 20 == 10 yields: "  
         << (20 == 10) << endl;  
}  
```  
  
 等値演算子は、同じ型のメンバーへのポインターを比較できます。 このような比較の場合は、メンバーへのポインター変換が実行されます。 メンバーへのポインターは、0 として評価される定数式と比較することもできます。  
  
## <a name="see-also"></a>参照  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 関係演算子と等値演算子](../c-language/c-relational-and-equality-operators.md)