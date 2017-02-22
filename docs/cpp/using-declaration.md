---
title: "using 宣言 | Microsoft Docs"
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
  - "using 宣言"
  - "名前空間の宣言、名前空間で修飾されていない名前"
  - "宣言 [C++]、using 宣言"
  - "名前空間 [C++]、修飾されていない名前"
  - "using キーワード [C++]"
  - "宣言 [C++]、名前空間"
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# using 宣言
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`using` 宣言を使用すると、 `using` 宣言があるスコープ内に名前を定義できます。  
  
## 構文  
  
```  
  
      using [typename][::] nested-name-specifier unqualified-id  
using :: unqualified-id  
```  
  
## 解説  
 その名前は、他の場所で宣言されたエンティティのシノニムになります。  特定の名前空間から個々の名前を[明示的な修飾](../misc/explicit-qualification.md)なしで使用できるようになります。  これは、名前空間内のすべての名前を修飾なしで使用できるようにする `using` ディレクティブとは対照的です。  詳細については、「[using ディレクティブ](../misc/using-directive-cpp.md)」を参照してください。  このキーワードは[型のエイリアス](../cpp/aliases-and-typedefs-cpp.md)にも使用されます。  
  
## 使用例  
 using 宣言は、クラス定義で使用できます。  
  
```cpp  
// using_declaration1.cpp  
#include <stdio.h>  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class D : B {  
public:  
   using B::f;  
   using B::g;  
   void f(int) {  
      printf_s("In D::f()\n");  
      f('c');  
   }  
  
   void g(int) {  
      printf_s("In D::g()\n");  
      g('c');  
   }  
};  
  
int main() {  
   D myD;  
   myD.f(1);  
   myD.g('a');  
}  
```  
  
  **In D::f\(\)**  
**In B::f\(\)**  
**In B::g\(\)**   
## 使用例  
 メンバーの宣言に使用する場合、using 宣言は基底クラスのメンバーを参照する必要があります。  
  
```cpp  
// using_declaration2.cpp  
#include <stdio.h>  
  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class C {  
public:  
   int g();  
};  
  
class D2 : public B {  
public:  
   using B::f;   // ok: B is a base of D2  
   // using C::g;   // error: C isn't a base of D2  
};  
  
int main() {  
   D2 MyD2;  
   MyD2.f('a');  
}  
```  
  
  **In B::f\(\)**   
## 使用例  
 using 宣言で宣言されたメンバーは明示的な修飾で参照できます。  `::` プレフィックスは、グローバル名前空間を参照します。  
  
```cpp  
// using_declaration3.cpp  
#include <stdio.h>  
  
void f() {  
   printf_s("In f\n");  
}  
  
namespace A {  
   void g() {  
      printf_s("In A::g\n");  
   }  
}  
  
namespace X {  
   using ::f;   // global f  
   using A::g;   // A's g  
}  
  
void h() {  
   printf_s("In h\n");  
   X::f();   // calls ::f  
   X::g();   // calls A::g  
}  
  
int main() {  
   h();  
}  
```  
  
  **In h**  
**In f**  
**In A::g**   
## 使用例  
 using 宣言を行うと、宣言によって作成されるシノニムは、using 宣言の時点で有効である定義のみを参照します。  using 宣言の後で名前空間に追加される定義は、無効なシノニムです。  
  
 using 宣言で定義された名前は元の名前のエイリアスです。  using 宣言は元の宣言の型、リンケージ、またはその他の属性には影響しません。  
  
```cpp  
// post_declaration_namespace_additions.cpp  
// compile with: /c  
namespace A {  
   void f(int) {}  
}  
  
using A::f;   // f is a synonym for A::f(int) only  
  
namespace A {  
   void f(char) {}  
}  
  
void f() {  
   f('a');   // refers to A::f(int), even though A::f(char) exists  
}  
  
void b() {  
   using A::f;   // refers to A::f(int) AND A::f(char)  
   f('a');   // calls A::f(char);  
}  
```  
  
## 使用例  
 名前空間内の関数では、1 つの名前のローカル宣言と using 宣言が同じスコープ内にある場合、それらはすべて同じエンティティ、つまり関数を参照している必要があります。  
  
```cpp  
// functions_in_namespaces1.cpp  
// C2874 expected  
namespace B {  
    int i;  
    void f(int);  
    void f(double);  
}  
  
void g() {  
    int i;  
    using B::i;   // error: i declared twice  
    void f(char);  
    using B::f;   // ok: each f is a function  
}  
```  
  
 この例では、`using B::i` ステートメントにより、2 つ目の `int i` が `g()` 関数で宣言されます。  `B::f` 内に定義された関数名に異なるパラメーター型があるため、`using B::f` ステートメントと `f(char)` 関数は競合しません。  
  
## 使用例  
 ローカル関数宣言は、using 宣言で定義された関数と同じ名前および型を含むことはできません。  たとえば、次のようになります。  
  
```cpp  
// functions_in_namespaces2.cpp  
// C2668 expected  
namespace B {  
    void f(int);  
    void f(double);  
}  
  
namespace C {  
    void f(int);  
    void f(double);  
    void f(char);  
}  
  
void h() {  
    using B::f;          // introduces B::f(int) and B::f(double)  
    using C::f;          // C::f(int), C::f(double), and C::f(char)  
    f('h');              // calls C::f(char)  
    f(1);                // C2668 ambiguous: B::f(int) or C::f(int)?  
    void f(int);         // C2883 conflicts with B::f(int) and C::f(int)  
}  
```  
  
## 使用例  
 継承では、using 宣言で基底クラスの名前を派生クラスのスコープ内に定義すると、派生クラスのメンバー関数によって、基底クラスで同じ名前と引数の型を持つ仮想メンバー関数がオーバーライドされます。  
  
```cpp  
// using_declaration_inheritance1.cpp  
#include <stdio.h>  
struct B {  
   virtual void f(int) {  
      printf_s("In B::f(int)\n");  
   }  
  
   virtual void f(char) {  
      printf_s("In B::f(char)\n");  
   }  
  
   void g(int) {  
      printf_s("In B::g\n");  
   }  
  
   void h(int);  
};  
  
struct D : B {  
   using B::f;  
   void f(int) {   // ok: D::f(int) overrides B::f(int)  
      printf_s("In D::f(int)\n");  
   }  
  
   using B::g;  
   void g(char) {   // ok: there is no B::g(char)  
      printf_s("In D::g(char)\n");  
   }  
  
   using B::h;  
   void h(int) {}   // Note: D::h(int) hides non-virtual B::h(int)  
};  
  
void f(D* pd) {  
   pd->f(1);   // calls D::f(int)  
   pd->f('a');   // calls B::f(char)  
   pd->g(1);   // calls B::g(int)  
   pd->g('a');   // calls D::g(char)  
}  
  
int main() {  
   D * myd = new D();  
   f(myd);  
}  
```  
  
  **In D::f\(int\)**  
**In B::f\(char\)**  
**In B::g**  
**In D::g\(char\)**   
## 使用例  
 using 宣言で定義された名前のすべてのインスタンスはアクセス可能である必要があります。  特に、派生クラスが基底クラスのメンバーにアクセスするために using 宣言を使用する場合は、そのメンバー名がアクセス可能である必要があります。  名前がオーバーロードされたメンバー関数の名前である場合、その名前のすべての関数にアクセス可能である必要があります。  
  
 メンバーのアクセシビリティの詳細については、「[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)」を参照してください。  
  
```cpp  
// using_declaration_inheritance2.cpp  
// C2876 expected  
class A {  
private:  
   void f(char);  
public:  
   void f(int);  
protected:  
   void g();  
};  
  
class B : public A {  
   using A::f;   // C2876: A::f(char) is inaccessible  
public:  
   using A::g;   // B::g is a public synonym for A::g  
};  
```  
  
## 参照  
 [名前空間](../cpp/namespaces-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)