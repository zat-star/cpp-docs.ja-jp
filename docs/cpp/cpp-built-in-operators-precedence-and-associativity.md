---
title: "C++ 組み込み演算子、優先順位と結合 |Microsoft ドキュメント"
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
- operators (C++), hierarchy
- operator precedence
- precedence, operators
- operators (C++), associativity
- multiple operators [C++]
- associativity of operators [C++]
- operators [C++], precedence
- evaluation order
- hierarchy, operator
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
caps.latest.revision: 13
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
ms.openlocfilehash: 6c45b0d3ff2aaee6763b73949727dcde5ee744bc
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++ 組み込み演算子、優先順位と結合規則
C++ 言語には、C のすべての演算子が含まれており、いくつかの新しい演算子が追加されています。 演算子により、1 つまたは複数のオペランドに対して実行される評価が決まります。  
  
 演算子の優先順位により、複数の演算子を含む式で、どの演算子から先に演算を行うかが決まります。 演算子の結合規則により、優先順位が同じ複数の演算子を含む式で、オペランドを左右どちらの演算子にグループ化するかが決まります。 次の表では、C++ の演算子の優先順位と結合規則を示しています (演算子は優先順位の高いものから低いものの順に並んでいます)。 優先順位番号が同じ演算子は、別の関係がかっこで明示的に適用されない限り、同じ優先順位になります。  
  
### <a name="c-operator-precedence-and-associativity"></a>C++ 演算子の優先順位と結合規則  
  
|演算子の説明|演算子|  
|--------------------------|--------------|  
|`Group 1 precedence, no associativity`|  
|[スコープ解決演算子](../cpp/scope-resolution-operator.md)|`::`|  
|`Group 2 precedence, left to right associativity`|  
|[メンバー選択 (オブジェクトまたはポインター)](../cpp/member-access-operators-dot-and.md)|`. or ->`|  
|[配列の添字](../cpp/subscript-operator.md)|`[ ]`|  
|[関数呼び出し](../cpp/function-call-operator-parens.md)|`( )`|  
|[後置インクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[後置デクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`--`|  
|[型名](../cpp/typeid-operator.md)|`typeid( )`|  
|[定数の型変換](../cpp/const-cast-operator.md)|`const_cast`|  
|[動的な型変換](../cpp/dynamic-cast-operator.md)|`dynamic_cast`|  
|[再解釈型変換](../cpp/reinterpret-cast-operator.md)|`reinterpret_cast`|  
|[静的な型変換](../cpp/static-cast-operator.md)|`static_cast`|  
|`Group 3 precedence, right to left associativity`|  
|[オブジェクトまたは型のサイズ](../cpp/sizeof-operator.md)|`sizeof`|  
|[前置インクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[前置デクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`--`|  
|[1 の補数](../cpp/one-s-complement-operator-tilde.md)|`~`|  
|[論理 not](../cpp/logical-negation-operator-exclpt.md)|`!`|  
|[単項マイナス符号](../cpp/unary-plus-and-negation-operators-plus-and.md)|`-`|  
|[単項プラス](../cpp/unary-plus-and-negation-operators-plus-and.md)|`+`|  
|[アドレスの](../cpp/lvalue-reference-declarator-amp.md)|`&`|  
|[間接参照](../cpp/indirection-operator-star.md)|`*`|  
|[オブジェクトを作成します。](../cpp/new-operator-cpp.md)|`new`|  
|[オブジェクトを破棄します。](../cpp/delete-operator-cpp.md)|`delete`|  
|[キャスト](../cpp/cast-operator-parens.md)|`Cast: ()`|  
|`Group 4 precedence, left to right associativity`|  
|[ポインター メンバーへの (オブジェクトまたはポインター)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|`.* or ->*`|  
|`Group 5 precedence, left to right associativity`|  
|[乗算](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`*`|  
|[除算](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`/`|  
|[剰余](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`%`|  
|`Group 6 precedence, left to right associativity`|  
|[追加](../cpp/additive-operators-plus-and.md)|`+`|  
|[減算](../cpp/additive-operators-plus-and.md)|`-`|  
|`Group 7 precedence, left to right associativity`|  
|[左シフト](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|`<<`|  
|[右シフト](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|`>>`|  
|`Group 8 precedence, left to right associativity`|  
|[小さい](../cpp/relational-operators-equal-and-equal.md)|`<`|  
|[大きい](../cpp/relational-operators-equal-and-equal.md)|`>`|  
|[以下に](../cpp/relational-operators-equal-and-equal.md)|`<=`|  
|[大きいまたは等しい](../cpp/relational-operators-equal-and-equal.md)|`>=`|  
|`Group 9 precedence, left to right associativity`|  
|[等しいかどうか](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`==`|  
|[非等値](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`!=`|  
|`Group 10 precedence left to right associativity`|  
|[ビットごとの AND](../cpp/bitwise-and-operator-amp.md)|`&`|  
|`Group 11 precedence, left to right associativity`|  
|[ビットごとの排他的 OR](../cpp/bitwise-exclusive-or-operator-hat.md)|`^`|  
|`Group 12 precedence, left to right associativity`|  
|[ビット演算子包含的 OR](../cpp/bitwise-inclusive-or-operator-pipe.md)|`&#124;`|  
|`Group 13 precedence, left to right associativity`|  
|[論理 AND](../cpp/logical-and-operator-amp-amp.md)|`&&`|  
|`Group 14 precedence, left to right associativity`|  
|[論理 OR](../cpp/logical-or-operator-pipe-pipe.md)|`&#124;&#124;`|  
|`Group 15 precedence, right to left associativity`|  
|[条件付き](../cpp/conditional-operator-q.md)|`? :`|  
|`Group 16 precedence, right to left associativity`|  
|[代入](../cpp/assignment-operators.md)|`=`|  
|[乗算代入](../cpp/assignment-operators.md)|`*=`|  
|[除算代入](../cpp/assignment-operators.md)|`/=`|  
|[剰余代入](../cpp/assignment-operators.md)|`%=`|  
|[加算代入](../cpp/assignment-operators.md)|`+=`|  
|[減算代入](../cpp/assignment-operators.md)|`-=`|  
|[左シフト代入](../cpp/assignment-operators.md)|`<<=`|  
|[右シフト代入](../cpp/assignment-operators.md)|`>>=`|  
|[ビットごとの AND 代入](../cpp/assignment-operators.md)|`&=`|  
|[ビット演算子包含的 OR 代入](../cpp/assignment-operators.md)|`&#124;=`|  
|[ビット演算子排他的 OR 代入](../cpp/assignment-operators.md)|`^=`|  
|`Group 17 precedence, right to left associativity`|  
|[throw 式](../cpp/try-throw-and-catch-statements-cpp.md)|`throw`|  
|`Group 18 precedence, left to right associativity`|  
|[コンマ](../cpp/comma-operator.md)|`,`|  
  
## <a name="see-also"></a>関連項目  
[演算子のオーバーロード](operator-overloading.md)



