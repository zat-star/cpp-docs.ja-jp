---
title: "Address-of 演算子: &amp; |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
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
ms.openlocfilehash: 56e2606759cc381c1ae6f6f4f1f7cbc1d9d2d810
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="address-of-operator-amp"></a>Address-of 演算子:&amp;
## <a name="syntax"></a>構文  
  
```  
& cast-expression  
```  
  
## <a name="remarks"></a>コメント  
 単項 address-of 演算子 (**&**)、オペランドのアドレスを取得します。 アドレス演算子のオペランドは、関数指定子です。または、ビット フィールドではなく、**register** ストレージ クラス指定子で宣言されていないオブジェクトを指定する左辺値です。  
  
 アドレス演算子は、ファイル スコープ レベルで宣言された基本型、構造体型、クラス型、または共用体型を持つ変数、または添字配列参照だけに適用できます。 これらの式では、アドレス演算子を含まない定数式を、アドレス式に加算したりアドレス式から減算できます。  
  
 関数または左辺値に適用されたときの式の結果は、オペランドの型から派生したポインター型 (右辺値) です。 たとえば、オペランドが `char` 型の場合、式の結果は `char` へのポインター型になります。 アドレスの演算子に適用される**const**または`volatile`オブジェクトの場合に評価**const** `type` ** \* **または`volatile` `type`** \***ここで、`type`元のオブジェクトの種類です。  
  
 アドレス演算子を適用すると、[修飾名](http://msdn.microsoft.com/en-us/3fefb16d-8120-4627-8b3f-3d90fbdcd1df)、結果は異なるかどうか、*修飾名*静的メンバーを指定します。 その場合、結果はメンバーの宣言で指定した型へのポインターです。 メンバーが静的でない場合、結果は、メンバーへのポインターは*名前*で示されたクラスの*修飾クラス名*です。 (を参照してください[一次式](../cpp/primary-expressions.md)について*修飾クラス名*)。次のコードは、メンバーが静的かどうかによって、どのように結果が違うかを示します。  
  
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
  
 この例では、`&PTM::fValue` 式は、`float *` が静的メンバーであるため、`float PTM::*` 型の代わりに `fValue` を生成します。  
  
 オーバーロード関数のアドレスは、どのバージョンの関数が参照されているかが明らかな場合にのみ受け取ることができます。 参照してください[関数のオーバー ロード](function-overloading.md)特定のアドレスを取得する方法については、関数をオーバー ロードします。  
  
 参照型にアドレス演算子を適用すると、参照がバインドされたオブジェクトに演算子を適用するのと同じ結果を生成します。 例:  
  
## <a name="example"></a>例  
  
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
  
## <a name="output"></a>出力  
  
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
  
## <a name="output"></a>出力  
  
```  
25  
```  
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [左辺値参照宣言子: &](../cpp/lvalue-reference-declarator-amp.md)   
 [間接演算子とアドレス演算子](../c-language/indirection-and-address-of-operators.md)

