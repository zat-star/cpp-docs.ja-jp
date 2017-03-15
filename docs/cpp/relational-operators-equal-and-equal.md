---
title: "関係演算子: &lt;、&gt;、&lt;=、&gt;= | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "<"
  - ">"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "< 演算子"
  - "<= 演算子"
  - "> 演算子"
  - ">= 演算子"
  - "大なり演算子"
  - "以上演算子"
  - "小なり演算子"
  - "以下演算子"
  - "関係演算子, 構文"
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 関係演算子: &lt;、&gt;、&lt;=、&gt;=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
        expression < expression  
expression > expression  
expression <= expression  
expression >= expression  
```  
  
## 解説  
 二項関係演算子は次のリレーションシップを判断します。  
  
-   より小さい \(**\<**\)  
  
-   より大きい \(**\>**\)  
  
-   以下 \(**\<\=**\)  
  
-   以上 \(**\>\=**\)  
  
 関係演算子の結合規則は、左から右方向です。  関係演算子のオペランドは、両方とも数値型またはポインター型である必要があります。  これらは型 `bool` の値を生成します。  式のリレーションシップが false の場合、返される値は **false** \(0\) です。それ以外の場合、返される値は **true** \(1\) です。  
  
## 使用例  
  
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
  
 前の例で、ストリーム挿入演算子 \(**\<\<**\) が関係演算子より高い優先順位を持つため、式をかっこで囲む必要があります。  したがって、かっこがない最初の式は次のように評価されます。  
  
```  
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");  
```  
  
 「[算術変換](../misc/arithmetic-conversions.md)」で説明する通常の算術変換は、数値型のオペランドに適用されます。  
  
## ポインターの比較  
 同じ型のオブジェクトへの 2 つのポインターを比較する場合、結果はプログラムのアドレス空間で指すオブジェクトの位置によって決まります。  ポインターは、0 または void \* 型のポインターに評価される定数式と比較することもできます。  ポインターの比較が void \* 型のポインターに対して行われた場合、他のポインターも暗黙的に void \* 型に変換されます。  次に、比較が行われます。  
  
 次の場合を除いて、異なる型の 2 つのポインターを比較することはできません。  
  
-   1 つの型が、他の型の派生クラス型である。  
  
-   ポインターのうち少なくとも 1 つが void \* 型に明示的に変換 \(キャスト\) される   \(他のポインターが変換で暗黙的に void \* 型に変換される\)。  
  
 同じオブジェクトを指す同じ型の 2 つのポインターは、等しい結果になることが保証されています。  オブジェクトの非静的メンバーへの 2 つのポインターを比較する場合、次の規則が適用されます。  
  
-   クラス型が共用体でない場合、および 2 つのメンバーがアクセス指定子で区切られない場合 \(パブリック、プロテクト、プライベートなど\)、最後に宣言されたメンバーへのポインターは、以前に宣言されたメンバーへのポインターよりも大きいと見なされます   \(アクセス指定子の詳細については、「*アクセス指定子*」の「構文」セクションを参照してください\)[](../misc/access-specifiers.md "Access Specifiers")。  
  
-   2 つのメンバーがアクセス指定子で区切られる場合、結果は未定義になります。  
  
-   クラス型が共用体である場合は、その共用体の異なるデータ メンバーへのポインターが等しいと見なされます。  
  
 2 個のポインターが、同じ配列の要素、または配列の末尾の次の位置の要素をポイントしている場合、より上位の添字を持つオブジェクトへのポインターが高く評価されます。  ポインターの比較は、ポインターが同じ配列のオブジェクトまたは配列の末尾の次の位置を参照している場合にのみ、有効であると保証されます。  
  
## 参照  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 関係演算子と等値演算子](../c-language/c-relational-and-equality-operators.md)