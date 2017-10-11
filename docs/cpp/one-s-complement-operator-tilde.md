---
title: "1 つ &#39; s ごとの補数演算子: ~ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ~
dev_langs:
- C++
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 918555af04d20be2533b488ee26f031e10a54ca4
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="one39s-complement-operator-"></a>1 つ &#39; s ごとの補数演算子: ~
## <a name="syntax"></a>構文  
  
```  
  
~ cast-expression  
```  
  
## <a name="remarks"></a>コメント  
 1 の補数演算子 (`~`) は、"ビット補数" 演算子とも呼ばれ、オペランドのビットごとの 1 の補数を生成します。 つまり、オペランドの各ビットが 1 である場合の結果は、0 になります。 逆に、オペランドの各ビットが 0 である場合の結果は、1 になります。 1 の補数演算子のオペランドは、整数型である必要があります。  
  
## <a name="operator-keyword-for-"></a>~ の演算子キーワード  
 `compl` 演算子は `~` の代替表現です。 アクセスする方法を次の 2 つが、`compl`をプログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、使用してコンパイル[/Za](../build/reference/za-ze-disable-language-extensions.md)です。  
  
## <a name="example"></a>例  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 この例では、`y` に割り当てられた新しい値は、符号なしの値 0xFFFF の 1 の補数、つまり 0x0000 です。  
  
 整数の上位変換は、整数オペランドに対して実行され、結果の型は、そのオペランドが昇格される型になります。 参照してください[標準変換](standard-conversions.md)昇格を実行する方法の詳細についてです。  
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [単項算術演算子](../c-language/unary-arithmetic-operators.md)
