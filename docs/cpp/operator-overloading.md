---
title: "演算子のオーバーロード | Microsoft Docs"
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
  - "operator_cpp"
  - "operator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "再定義不可演算子"
  - "operator キーワード [C++]"
  - "演算子のオーバーロード"
  - "演算子 [C++], オーバーロード"
  - "再定義可能な演算子"
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 演算子のオーバーロード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`operator` キーワードは、クラスのインスタンスに適用されたときの `operator-symbol` の意味を指定する関数を宣言します。  これによって、演算子に複数の意味を与えます \(つまり、"オーバーロード" します\)。  コンパイラは、オペランドの型を検査することにより、演算子の異なる意味を区別します。  
  
## 構文  
  
```  
  
type operator operator-symbol ( parameter-list )  
```  
  
## 解説  
 ほとんどの組み込み演算子の関数をグローバルに、またはクラス単位で定義し直すことができます。  オーバーロードされた演算子は、関数として実装されます。  
  
 オーバーロードされた演算子の名前は、`operator``x` です。`x` は次の表に示すような演算子です。  たとえば、加算演算子をオーバーロードするために、`operator+` と呼ばれる関数を定義します。  同様に、加算\/代入演算子 `+=` をオーバーロードするには、`operator+=` という名前の関数を定義します。  
  
### 再定義可能な演算子  
  
|演算子|名前|種類|  
|---------|--------|--------|  
|`,`|コンマ|2 項|  
|`!`|論理 NOT|単項|  
|`!=`|非等値|2 項|  
|`%`|剰余|2 項|  
|`%=`|剰余代入|2 項|  
|`&`|ビットごとの AND|2 項|  
|`&`|アドレス取得|単項|  
|`&&`|論理 AND|2 項|  
|`&=`|ビットごとの AND 代入|2 項|  
|`( )`|関数呼び出し|—|  
|`( )`|キャスト演算子|単項|  
|`*`|乗算|2 項|  
|`*`|ポインター逆参照|単項|  
|`*=`|乗算代入|2 項|  
|`+`|加算|2 項|  
|`+`|単項プラス|単項|  
|`++`|インクリメント <sup>1</sup>|単項|  
|`+=`|加算代入|2 項|  
|`–`|減算|2 項|  
|`–`|単項マイナス符号|単項|  
|`––`|デクリメント <sup>1</sup>|単項|  
|`–=`|減算代入|2 項|  
|`–>`|メンバー選択|2 項|  
|`–>*`|メンバーへのポインター選択|2 項|  
|`/`|除算記号|2 項|  
|`/=`|除算代入|2 項|  
|`<`|より小さい|2 項|  
|`<<`|左シフト|2 項|  
|`<<=`|左シフト代入|2 項|  
|`<=`|以下|2 項|  
|`=`|代入|2 項|  
|`==`|等価比較|2 項|  
|`>`|より大きい|2 項|  
|`>=`|以上|2 項|  
|`>>`|右シフト|2 項|  
|`>>=`|右シフト代入|2 項|  
|`[ ]`|配列添字|—|  
|`^`|排他的 OR|2 項|  
|`^=`|排他的 OR 代入|2 項|  
|`&#124;`|ビットごとの包括的 OR|2 項|  
|`&#124;=`|ビットごとの包括的 OR 代入|2 項|  
|`&#124;&#124;`|論理 OR|2 項|  
|`~`|1 の補数|単項|  
|`delete`|`Delete`|—|  
|`new`|`New`|—|  
|`conversion operators`|変換演算子|単項|  
  
 1   単項インクリメントおよびデクリメント演算子には、前置インクリメントと後置インクリメントの 2 種類のバージョンがあります。  
  
 詳細については、「[演算子のオーバーロードに関する一般的な規則](../cpp/general-rules-for-operator-overloading.md)」を参照してください。  さまざまなカテゴリのオーバーロードされた演算子に対する制約については、次のトピックを参照してください。  
  
-   [単項演算子](../cpp/overloading-unary-operators.md)  
  
-   [二項演算子](../cpp/binary-operators.md)  
  
-   [代入](../cpp/assignment.md)  
  
-   [関数呼び出し](../Topic/Function%20Call%20\(C++\).md)  
  
-   [添字演算子](../cpp/subscripting.md)  
  
-   [クラス メンバーに対するアクセス](../Topic/Member%20Access.md)  
  
-   [インクリメントとデクリメント](../Topic/Increment%20and%20Decrement%20Operator%20Overloading%20\(C++\).md)  
  
-   [変換](../cpp/user-defined-type-conversions-cpp.md)  
  
 次のテーブルに示す演算子は、オーバーロードできません。  テーブルにはプリプロセッサ シンボル `#` および `##` が含まれます。  
  
### 再定義不可演算子  
  
|||  
|-|-|  
|`Operator`|`Name`|  
|`.`|メンバー選択|  
|`.*`|メンバーへのポインター選択|  
|`::`|スコープ解決|  
|`?  :`|条件|  
|`#`|プリプロセッサによる文字列への変換|  
|`##`|プリプロセッサによる連結|  
  
 オーバーロードされた演算子は通常、コードに出現すると、コンパイラによって暗黙的に呼び出されますが、メンバーまたは非メンバー関数を呼び出すのと同じ方法で明示的に呼び出すことができます。  
  
```  
Point pt;  
pt.operator+( 3 );  // Call addition operator to add 3 to pt.  
```  
  
## 使用例  
 次の例では、`+` 演算子をオーバーロードして、2 つの複素数を加算して結果を返すようにします。  
  
```  
// operator_overloading.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Complex {  
   Complex( double r, double i ) : re(r), im(i) {}  
   Complex operator+( Complex &other );  
   void Display( ) {   cout << re << ", " << im << endl; }  
private:  
   double re, im;  
};  
  
// Operator overloaded using a member function  
Complex Complex::operator+( Complex &other ) {  
   return Complex( re + other.re, im + other.im );  
}  
  
int main() {  
   Complex a = Complex( 1.2, 3.4 );  
   Complex b = Complex( 5.6, 7.8 );  
   Complex c = Complex( 0.0, 0.0 );  
  
   c = a + b;  
   c.Display();  
}  
```  
  
## 出力  
  
```  
6.8, 11.2  
```  
  
## このセクションの内容  
  
1.  [演算子のオーバーロードに関する一般的な規則](../cpp/general-rules-for-operator-overloading.md)  
  
2.  [単項演算子のオーバーロード](../cpp/overloading-unary-operators.md)  
  
3.  [二項演算子](../cpp/binary-operators.md)  
  
4.  [代入](../cpp/assignment.md)  
  
5.  [関数呼び出し](../Topic/Function%20Call%20\(C++\).md)  
  
6.  [添字演算子](../cpp/subscripting.md)  
  
7.  [メンバー アクセス](../Topic/Member%20Access.md)  
  
## 参照  
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)