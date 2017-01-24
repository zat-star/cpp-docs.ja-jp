---
title: "address-of 演算子: &amp; | Microsoft Docs"
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
  - "address-of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& 演算子"
  - "& 演算子, address-of 演算子"
  - "address-of 演算子 (&)"
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# address-of 演算子: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
& cast-expression  
```  
  
## 解説  
 単項アドレス演算子 \(**&**\) は、オペランドのアドレスを受け取ります。  アドレス演算子のオペランドは、関数指定子です。または、ビット フィールドではなく、**register** ストレージ クラス指定子で宣言されていないオブジェクトを指定する左辺値です。  
  
 アドレス演算子は、ファイル スコープ レベルで宣言された基本型、構造体型、クラス型、または共用体型を持つ変数、または添字配列参照だけに適用できます。  これらの式では、アドレス演算子を含まない定数式を、アドレス式に加算したりアドレス式から減算できます。  
  
 関数または左辺値に適用されたときの式の結果は、オペランドの型から派生したポインター型 \(右辺値\) です。  たとえば、オペランドが `char` 型の場合、式の結果は `char` へのポインター型になります。  **const** または `volatile` オブジェクトに適用されるアドレス演算子は、**const** `type` **\*** または `volatile` `type` **\*** \(`type` は元のオブジェクトの型\) と評価されます。  
  
 アドレス演算子を[修飾された名前](http://msdn.microsoft.com/ja-jp/3fefb16d-8120-4627-8b3f-3d90fbdcd1df)に適用した場合、結果は *qualified\-name* が静的メンバーを指定しているかどうかに依存します。  その場合、結果はメンバーの宣言で指定した型へのポインターです。  メンバーが静的でない場合、結果は *qualified\-class\-name* で示されるクラスのメンバーの名前へのポインターになります  \(*qualified\-class\-name* に関する詳細については、「[1 次式](../cpp/primary-expressions.md)」を参照してください\)。 次のコードは、メンバーが静的かどうかによって、どのように結果が違うかを示します。  
  
```  
// expre_Address_Of_Operator.cpp  
// C2440 expected  
class PTM {  
public:  
           int   iValue;  
    static float fValue;  
};  
  
int main() {  
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static  
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static  
   float *spfValue     = &PTM::fValue;  // OK  
}  
```  
  
 この例では、`&PTM::fValue` 式は、`fValue` が静的メンバーであるため、`float PTM::*` 型の代わりに `float *` を生成します。  
  
 オーバーロード関数のアドレスは、どのバージョンの関数が参照されているかが明らかな場合にのみ受け取ることができます。  特定のオーバーロード関数のアドレスを取得する方法については、「[オーバーロード関数のアドレス](../misc/address-of-overloaded-functions.md)」を参照してください。  
  
 参照型にアドレス演算子を適用すると、参照がバインドされたオブジェクトに演算子を適用するのと同じ結果を生成します。  次に例を示します。  
  
## 使用例  
  
```  
// expre_Address_Of_Operator2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   double d;        // Define an object of type double.  
   double& rd = d;  // Define a reference to the object.  
  
   // Obtain and compare their addresses  
   if( &d == &rd )  
      cout << "&d equals &rd" << endl;  
}  
```  
  
## 出力  
  
```  
&d equals &rd  
```  
  
 次の例は、関数へのポインター引数を受け渡すためにアドレス演算子を使用します。  
  
```  
// expre_Address_Of_Operator3.cpp  
// compile with: /EHsc  
// Demonstrate address-of operator &  
  
#include <iostream>  
using namespace std;  
  
// Function argument is pointer to type int  
int square( int *n ) {  
   return (*n) * (*n);  
}  
  
int main() {  
   int mynum = 5;  
   cout << square( &mynum ) << endl;   // pass address of int  
}  
```  
  
## 出力  
  
```  
25  
```  
  
## 参照  
 [単項演算子を含む式](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [左辺値参照宣言子: &](../Topic/Lvalue%20Reference%20Declarator:%20&.md)   
 [間接演算子とアドレス演算子](../c-language/indirection-and-address-of-operators.md)