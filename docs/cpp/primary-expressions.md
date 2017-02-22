---
title: "一次式 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "式 [C++], リテラル"
  - "式 [C++], 名前"
  - "式 [C++], 主"
  - "式 [C++], 修飾名"
  - "一次式"
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 一次式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

基本式は、より複雑な式のビルド ブロックです。  つまり、リテラル、名前、スコープ解決演算子 \(`::`\) で修飾された名前です。基本式は次のいずれかの形式になります。  
  
```  
  
        literal  
this  
:: name  
name   
( expression )  
```  
  
 *literal* は定数基本式です。  その型は、リテラルの指定の形式によって決まります。  リテラルの指定の詳細については、「[リテラル](../cpp/numeric-boolean-and-pointer-literals-cpp.md)」を参照してください。  
  
 **this** キーワードはクラス オブジェクトへのポインターです。  非静的メンバー関数内で使用でき、その関数が呼び出されたクラスのインスタンスを参照します。  **this** キーワードはクラス メンバー関数の本体の外部で使用することはできません。  
  
 **this** ポインターの型は、明示的に **this** ポインターを変更しない関数内では、`type` **\*const** \(`type` はクラス名\) です。  次の例では、メンバー関数の宣言と **this** の型を示しています。  
  
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
  
 **this** ポインターの型の変更の詳細については、「[Type of this Pointer \(this ポインターの型\)](../misc/type-of-this-pointer.md)」を参照してください。  
  
 名前の前のスコープ解決演算子 \(`::`\) は基本式です。そのような名前は、メンバー名ではなく、グローバル スコープでの名前であることが必要です。この式の型は名前の宣言によって決まります。  宣言名が左辺値である場合は、左辺値 \(代入演算子式の左辺になる式\) です。  スコープ解決演算子を使用すると、グローバル名が現在のスコープでは隠されていても、その名前を参照できます。  スコープ解決演算子の使用例については、「[スコープ](../cpp/scope-visual-cpp.md)」を参照してください。  
  
 かっこで囲まれた式も基本式であり、その型と値はかっこで囲まれていない式のものと一致します。  この式は、かっこで囲まれていない式が左辺値であれば、左辺値です。  
  
 前に示している基本式の構文のコンテキストでは、*name* は「[Names \(名前\)](http://msdn.microsoft.com/ja-jp/1c49cc24-08d5-4884-b170-ba8ed42d80db)」で説明している構文で宣言されるいずれかの名前です。ただし、その名前の前にスコープ解決演算子を使用すると、クラス内にのみ出現する名前の型は受け入れられなくなります。このような名前には、ユーザー定義の変換関数やデストラクターの名前が該当します。  
  
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
  
 次に示しているのは、考えられるすべての *name* つまり基本式の、さまざまな形式の例です。  
  
```  
MyClass // a identifier  
MyClass::f // a qualified name  
operator = // an operator function name  
operator char* // a conversion operator function name  
~MyClass // a destructor name  
A::B   // a qualified name  
A<int> // a template id  
```  
  
## 参照  
 [式の型](../cpp/types-of-expressions.md)