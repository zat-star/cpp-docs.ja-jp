---
title: "後置インクリメント演算子と前置デクリメント演算子: + + および--|Microsoft ドキュメント"
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
- member-selection operators [C++]
- -- operator [C++], postfix decrement operators
- postfix operators [C++]
- ++ operator [C++], postfix increment operators
- decrement operators [C++], syntax
- operators [C++], postfix
- decrement operators [C++]
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
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
ms.openlocfilehash: b9e8939e810336150fe3d46be4c72ee1946aebcf
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="postfix-increment-and-decrement-operators--and---"></a>後置インクリメント演算子と後置デクリメント演算子: ++ および --
## <a name="syntax"></a>構文  
  
```  
postfix-expression ++  
postfix-expression --  
```  
  
## <a name="remarks"></a>コメント  
 C++ には、前置および後置のインクリメント演算子およびデクリメント演算子が用意されています。このセクションでは、後置インクリメント演算子および後置デクリメント演算子についてのみ説明します  (詳細については、次を参照してください[前置インクリメント演算子と前置デクリメント演算子](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)。)。2 つの違いは、後置表記法でオペレーターが後に表示される*後置式*プレフィックス表記で、演算子は前に表示されます。 一方、*式。* 次の例は、後置インクリメント演算子を示しています。  
  
```  
i++;  
```  
  
 後置インクリメント演算子 (`++`) を適用する効果は、オペランドの値が適切な型の 1 単位分、増加することです。 同様に、後置デクリメント演算子を適用の効果 (**--**) は、適切な型の 1 単位分、オペランドの値が減少しました。  
  
 後置のインクリメントことに注意する必要がデクリメント式は、式の値に評価または**より前のバージョン**それぞれの演算子のアプリケーションです。 インクリメントまたはデクリメント操作が行われる**後**オペランドが評価されます。 この問題は、後置インクリメントまたはデクリメント演算が、より大きな式のコンテキストで行われる場合にのみ発生します。  
  
 後置演算子を関数の引数に適用した場合、引数の値が関数に渡される前にインクリメントまたはデクリメントされる保証はありません。  詳細については、C++ 標準のセクション 1.9.17 を参照してください。  
  
 型のオブジェクトの配列へのポインターに後置インクリメント演算子を適用する**長い**実際には、ポインターの内部表現に 4 が加算されます。 この動作により、ポインターを参照していた、 * n*番目の要素を指すため、配列の (*n*+1) 番目の要素。  
  
 後置インクリメントと後置デクリメント演算子のオペランドは変更可能である必要があります (いない**const**) 演算またはポインター型の左辺値です。 結果の型はのと同じ、*後置式*が左辺値ではなくなりました。  
  
**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): オペランドの後置インクリメントまたはデクリメント演算子できない可能性があります型の`bool`します。
  
 次のコードは、後置インクリメント演算子を示しています。  
  
```  
// expre_Postfix_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 10;  
   cout << i++ << endl;  
   cout << i << endl;  
}  
```  
  
 列挙型に対する後置インクリメント演算および後置デクリメント演算はサポートされていません。  
  
```  
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## <a name="see-also"></a>関連項目  
 [後置式](../cpp/postfix-expressions.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 後置インクリメント演算子と後置デクリメント演算子](../c-language/c-postfix-increment-and-decrement-operators.md)
