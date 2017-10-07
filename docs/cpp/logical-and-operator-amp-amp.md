---
title: "論理 AND 演算子: &amp; &amp; |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&&'
dev_langs:
- C++
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5a594efcc987fba69ceb17e7e09d10470adab75f
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="logical-and-operator-ampamp"></a>論理 AND 演算子:&amp;&amp;
## <a name="syntax"></a>構文  
  
```  
  
expression   
&&  
 expression  
  
```  
  
## <a name="remarks"></a>コメント  
 論理 AND 演算子 (**&&**) ブール値を返します**true**両方のオペランドが場合**true**し、返します**false**それ以外の場合。 オペランドは、評価前に `bool` 型に暗黙的に変換され、結果は `bool` 型です。 論理 AND には左から右方向の結合規則があります。  
  
 論理 AND 演算子のオペランドが同じ型である必要はありませんが、整数型またはポインター型である必要があります。 オペランドは一般に関係式または等価式です。  
  
 最初のオペランドが完全に評価され、すべての副作用が完了した後で、論理 AND 式の評価が続行されます。  
  
 2 番目のオペランドは、最初のオペランドが true (ゼロ以外) と評価された場合にのみ、評価されます。 この評価により、論理 AND 式が false の場合に 2 番目のオペランドに不要な評価が行われないようになっています。 このショート サーキット評価を使用して、次の例に示すように、null ポインターの逆参照を防止できます。  
  
```  
char *pch = 0;  
...  
(pch) && (*pch = 'a');  
```  
  
 `pch` が null (0) であれば、式の右側は評価されません。 したがって、null ポインターを使用した代入が発生することはありません。  
  
## <a name="operator-keyword-for-"></a>&& の演算子キーワード  
 **と**演算子に相当するテキストは、 ** &&**です。 アクセスする方法を次の 2 つが、**と**をプログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、コンパイル時に、または、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語の拡張機能を無効にする) コンパイラ オプション。  
  
## <a name="example"></a>例  
  
```  
// expre_Logical_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical AND  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b && b < c yields "  
         << (a < b && b < c) << endl  
         << "The false expression "  
         << "a > b && b < c yields "  
         << (a > b && b < c) << endl;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 組み込み演算子の優先順位と結合規則](cpp-built-in-operators-precedence-and-associativity.md) [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 論理演算子](../c-language/c-logical-operators.md)
