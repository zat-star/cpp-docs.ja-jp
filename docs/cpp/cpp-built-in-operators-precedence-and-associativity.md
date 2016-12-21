---
title: "C++ の演算子、優先順位と結合規則 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "結合規則 (演算子の)"
  - "評価順序"
  - "階層構造, 演算子"
  - "複数の演算子"
  - "演算子の優先順位"
  - "演算子 [C++], 結合規則"
  - "演算子 [C++], 階層構造"
  - "演算子 [C++], 優先順位"
  - "優先順位, 演算子"
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ の演算子、優先順位と結合規則
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 言語には、C のすべての演算子が含まれており、いくつかの新しい演算子が追加されています。  演算子により、1 つまたは複数のオペランドに対して実行される評価が決まります。  
  
 演算子の優先順位により、複数の演算子を含む式で、どの演算子から先に演算を行うかが決まります。  演算子の結合規則により、優先順位が同じ複数の演算子を含む式で、オペランドを左右どちらの演算子にグループ化するかが決まります。  次の表では、C\+\+ の演算子の優先順位と結合規則を示しています \(演算子は優先順位の高いものから低いものの順に並んでいます\)。  優先順位番号が同じ演算子は、別の関係がかっこで明示的に適用されない限り、同じ優先順位になります。  
  
### C\+\+ 演算子の優先順位と結合規則  
  
|演算子の説明|演算子|  
|------------|---------|  
|`Group 1 precedence, no associativity`|  
|[スコープ解決](../cpp/scope-resolution-operator.md)|`::`|  
|`Group 2 precedence, left to right associativity`|  
|[メンバー選択 \(オブジェクトまたはポインター\)](../Topic/Member%20Access%20Operators:%20.%20and%20-%3E.md)|`. or –>`|  
|[配列添字](../Topic/Subscript%20Operator:.md)|`[ ]`|  
|[関数呼び出し](../cpp/function-call-operator-parens.md)|`( )`|  
|[後置インクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[後置デクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`––`|  
|[型名](../cpp/typeid-operator.md)|`typeid( )`|  
|[const 型変換](../Topic/const_cast%20Operator.md)|`const_cast`|  
|[動的型変換](../cpp/dynamic-cast-operator.md)|`dynamic_cast`|  
|[再解釈型変換](../cpp/reinterpret-cast-operator.md)|`reinterpret_cast`|  
|[静的型変換](../cpp/static-cast-operator.md)|`static_cast`|  
|`Group 3 precedence, right to left associativity`|  
|[オブジェクトまたは型のサイズ](../cpp/sizeof-operator.md)|`sizeof`|  
|[前置インクリメント](../Topic/Prefix%20Increment%20and%20Decrement%20Operators:%20++%20and%20--.md)|`++`|  
|[前置デクリメント](../Topic/Prefix%20Increment%20and%20Decrement%20Operators:%20++%20and%20--.md)|`––`|  
|[1 の補数](../cpp/one-s-complement-operator-tilde.md)|`~`|  
|[論理 NOT](../cpp/logical-negation-operator-exclpt.md)|`!`|  
|[単項マイナス符号](../misc/unary-negation-operator.md)|`-`|  
|[単項プラス](../cpp/unary-plus-and-negation-operators-plus-and.md)|`+`|  
|[アドレス取得](../Topic/Lvalue%20Reference%20Declarator:%20&.md)|`&`|  
|[間接](../cpp/indirection-operator-star.md)|`*`|  
|[オブジェクトの作成](../cpp/new-operator-cpp.md)|`new`|  
|[オブジェクトの破棄](../cpp/delete-operator-cpp.md)|`delete`|  
|[Cast](../Topic/Cast%20Operator:%20\(\).md)|`Cast: ()`|  
|`Group 4 precedence, left to right associativity`|  
|[メンバーへのポインター \(オブジェクトまたはポインター\)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|`.* or –>*`|  
|`Group 5 precedence, left to right associativity`|  
|[乗算](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`*`|  
|[除算](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`/`|  
|[剰余](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`%`|  
|`Group 6 precedence, left to right associativity`|  
|[加算](../cpp/additive-operators-plus-and.md)|`+`|  
|[減算](../cpp/additive-operators-plus-and.md)|`–`|  
|`Group 7 precedence, left to right associativity`|  
|[左シフト](../Topic/Left%20Shift%20and%20Right%20Shift%20Operators%20\(%3E%3E%20and%20%3C%3C\).md)|`<<`|  
|[右シフト](../Topic/Left%20Shift%20and%20Right%20Shift%20Operators%20\(%3E%3E%20and%20%3C%3C\).md)|`>>`|  
|`Group 8 precedence, left to right associativity`|  
|[より小さい](../cpp/relational-operators-equal-and-equal.md)|`<`|  
|[より大きい](../cpp/relational-operators-equal-and-equal.md)|`>`|  
|[以下](../cpp/relational-operators-equal-and-equal.md)|`<=`|  
|[以上](../cpp/relational-operators-equal-and-equal.md)|`>=`|  
|`Group 9 precedence, left to right associativity`|  
|[等価比較](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`==`|  
|[非等値](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`!=`|  
|`Group 10 precedence left to right associativity`|  
|[ビットごとの AND](../cpp/bitwise-and-operator-amp.md)|`&`|  
|`Group 11 precedence, left to right associativity`|  
|[ビットごとの排他的 OR](../cpp/bitwise-exclusive-or-operator-hat.md)|`^`|  
|`Group 12 precedence, left to right associativity`|  
|[ビットごとの包括的 OR](../cpp/bitwise-inclusive-or-operator-pipe.md)|`&#124;`|  
|`Group 13 precedence, left to right associativity`|  
|[論理 AND](../Topic/Logical%20AND%20Operator:%20&&.md)|`&&`|  
|`Group 14 precedence, left to right associativity`|  
|[論理 OR](../cpp/logical-or-operator-pipe-pipe.md)|`&#124;&#124;`|  
|`Group 15 precedence, right to left associativity`|  
|[条件](../cpp/conditional-operator-q.md)|`? :`|  
|`Group 16 precedence, right to left associativity`|  
|[代入](../cpp/assignment-operators.md)|`=`|  
|[乗算代入](../cpp/assignment-operators.md)|`*=`|  
|[除算代入](../cpp/assignment-operators.md)|`/=`|  
|[剰余代入](../cpp/assignment-operators.md)|`%=`|  
|[加算代入](../cpp/assignment-operators.md)|`+=`|  
|[減算代入](../cpp/assignment-operators.md)|`–=`|  
|[左シフト代入](../cpp/assignment-operators.md)|`<<=`|  
|[右シフト代入](../cpp/assignment-operators.md)|`>>=`|  
|[ビットごとの AND 代入](../cpp/assignment-operators.md)|`&=`|  
|[ビットごとの包括的 OR 代入](../cpp/assignment-operators.md)|`&#124;=`|  
|[ビットごとの排他的 OR 代入](../cpp/assignment-operators.md)|`^=`|  
|`Group 17 precedence, right to left associativity`|  
|[throw 式](../cpp/try-throw-and-catch-statements-cpp.md)|`throw`|  
|`Group 18 precedence, left to right associativity`|  
|[コンマ](../cpp/comma-operator.md)|`,`|  
  
## 参照  
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [演算子のオーバーロード](../cpp/operator-overloading.md)