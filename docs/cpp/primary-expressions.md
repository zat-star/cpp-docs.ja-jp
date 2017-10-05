---
title: "一次式 |Microsoft ドキュメント"
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
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
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
ms.openlocfilehash: 2ba603c19a88849c15c9402e21d2acf39bb9f54d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="primary-expressions"></a>一次式
基本式は、より複雑な式のビルド ブロックです。 つまり、リテラル、名前、スコープ解決演算子 (`::`) で修飾された名前です。  基本式は次のいずれかの形式になります。  
  
```  
  
      literal  
      this  
:: namename( expression )  
```  
  
 A*リテラル*は定数基本式です。 その型は、リテラルの指定の形式によって決まります。 参照してください[リテラル](../cpp/numeric-boolean-and-pointer-literals-cpp.md)詳細については、リテラルを指定します。  
  
 **この**キーワードはクラス オブジェクトへのポインター。 非静的メンバー関数内で使用でき、その関数が呼び出されたクラスのインスタンスを参照します。 **この**クラス メンバー関数の本体の外側キーワードは使用できません。  
  
 型、**この**ポインターが`type` ** \*const** (ここで`type`クラスの名前を指定) 以外に変更する関数内で、**この**ポインター。 次の例は、関数宣言との型にメンバーを示します**この**:  
  
```  
// expre_Primary_Expressions.cpp  
// compile with: /LD  
class Example  
{  
public:  
    void Func();          //  * const this  
    void Func() const;    //  const * const this  
    void Func() volatile; //  volatile * const this  
};  
```  
  
 参照してください[このポインター](this-pointer.md)の型を変更する方法について、**この**ポインター。  
  
 名前の前のスコープ解決演算子 (`::`) は基本式です。  そのような名前は、メンバー名ではなく、グローバル スコープでの名前であることが必要です。  この式の型は名前の宣言によって決まります。 宣言名が左辺値である場合は、左辺値 (代入演算子式の左辺になる式) です。 スコープ解決演算子を使用すると、グローバル名が現在のスコープでは隠されていても、その名前を参照できます。 参照してください[スコープ](../cpp/scope-visual-cpp.md)スコープ解決演算子を使用する方法の例についてはします。  
  
 かっこで囲まれた式も基本式であり、その型と値はかっこで囲まれていない式のものと一致します。 この式は、かっこで囲まれていない式が左辺値であれば、左辺値です。  
  
 プライマリの式の構文が、上記のコンテキストで*名前*意味を説明する構文では何も[名](http://msdn.microsoft.com/en-us/1c49cc24-08d5-4884-b170-ba8ed42d80db)がときに、名前、種類の名前の前に、スコープ解決演算子を使用クラスでのみ発生することが許可されていません。  このような名前には、ユーザー定義の変換関数やデストラクターの名前が該当します。  
  
 次に示しているのは、基本式の例です。  
  
```  
100 // literal  
'c' // literal  
this // in a member function, a pointer to the class instance  
::func // a global function  
::operator + // a global operator function  
::A::B // a global qualified name  
( i + 1 ) // a parenthesized expression  
```  
  
 次の例はすべてと見なされます*名*、さまざまな形式で、つまり基本式。  
  
```  
MyClass // a identifier  
MyClass::f // a qualified name  
operator = // an operator function name  
operator char* // a conversion operator function name  
~MyClass // a destructor name  
A::B   // a qualified name  
A<int> // a template id  
```  
  
## <a name="see-also"></a>関連項目  
 [式の型](../cpp/types-of-expressions.md)
