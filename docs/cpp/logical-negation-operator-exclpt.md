---
title: "論理否定演算子: ! | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs: C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f63d36fc5974241fb624dd3a2afc863142516e9b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="logical-negation-operator-"></a>論理否定演算子: !
## <a name="syntax"></a>構文  
  
```  
  
! cast-expression  
```  
  
## <a name="remarks"></a>コメント  
 論理否定演算子 (**!**) のオペランドの意味を反転させます。 オペランドは、数値型またはポインター型 (または、数値型またはポインター型に評価される式) である必要があります。 オペランドは `bool` 型に暗黙的に変換されます。 結果は**true**場合は、変換されたオペランドが**false**; 結果は**false**場合は、変換されたオペランドが**true**です。 結果は `bool` 型です。  
  
 式の*e*、単項式**!***e* 式と同じ**(***e* `==` 0)、オーバー ロードされた演算子が関係する場所を除く。  
  
## <a name="operator-keyword-for-"></a>! の演算子キーワード  
 **いない**演算子に相当するテキストは、 **!**です。 アクセスの 2 つの方法、**いない**をプログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、コンパイル時に、または、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語の拡張機能を無効にする) コンパイラ オプション。  
  
## <a name="example"></a>例  
  
```  
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## <a name="see-also"></a>参照  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [単項算術演算子](../c-language/unary-arithmetic-operators.md)