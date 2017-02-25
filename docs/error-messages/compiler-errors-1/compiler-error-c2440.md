---
title: "コンパイラ エラー C2440 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2440"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2440"
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# コンパイラ エラー C2440
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'変換' : 'type1' から 'type2' に変換できません。  
  
 '`type1`' から '`type2`' にキャストできません。  
  
## 使用例  
 C2440 は、コンパイラ準拠オプション [\/Zc:strictStrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) が設定されている場合に、C\+\+ コードで文字列リテラルを使用して非定数の `char*` \(または `wchar_t*`\) を初期化しようとすると発生します。  C の場合、リテラル文字列の型は `char` の配列ですが、C\+\+ の場合は `const` `char` の配列です。  次の例では C2440 エラーが生成されます。  
  
```cpp  
// C2440s.cpp  
// Build: cl /Zc:strictStrings /W3 C2440s.cpp  
// When built, the compiler emits:  
// error C2440: 'initializing' : cannot convert from 'const char [5]'   
// to 'char *'  
//        Conversion from string literal loses const qualifier (see  
// /Zc:strictStrings)  
  
int main() {  
   char* s1 = "test"; // C2440  
   const char* s2 = "tests"; // OK  
}  
```  
  
## 使用例  
 C2440 は、メンバーへのポインターを void\* に変換しようとして発生することもあります。  次の例では C2440 が生成されます。  
  
```cpp  
// C2440.cpp  
class B {  
public:  
   void  f(){;}  
  
   typedef void (B::*pf)();  
  
   void f2(pf pf) {  
       (this->*pf)();  
       void* pp = (void*)pf;   // C2440  
   }  
  
   void f3() {  
      f2(f);  
   }  
};  
```  
  
## 使用例  
 C2440 は、事前宣言するだけで定義されていない型をキャストしようとした場合にも発生することがあります。  次の例では C2440 エラーが生成されます。  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## 使用例  
 次の例の 15 行目と 16 行目の C2440 エラーには、"`Incompatible calling conventions for UDT return value` \(UDT 戻り値の呼び出し規約に互換性がありません\)" というメッセージが表示されます。UDT とは、クラス、構造体、共用体などのユーザー定義型です。このような種類の非互換性エラーが発生するのは、事前宣言の戻り値の型で指定された UDT の呼び出し規約が UDT の実際の呼び出し規約と競合する場合や、関数ポインターが関連する場合です。  
  
 この例では、最初に、構造体およびその構造体を返す関数の事前宣言があります。コンパイラでは、この構造体で C\+\+ 呼び出し規約が使用されると仮定します。  次に、構造体の定義があります。既定では、この定義は C 呼び出し規約を使用します。  コンパイラでは、構造体全体の読み込みが完了するまでは、その構造体の呼び出し規約がわからないため、`get_c2` の戻り値の型での構造体の呼び出し規約も C\+\+ であると仮定します。  
  
 構造体の後には構造体を返す別の関数宣言が続きますが、この時点では、コンパイラは構造体の呼び出し規約が C\+\+ であることを認識しています。  同様に、構造体を返す関数ポインターは構造体定義の後に定義されているため、コンパイラはその構造体で C\+\+ 呼び出し規約が使用されることを認識します。  
  
 互換性のない 2 つの呼び出し規約が原因で発生する C2440 エラーを解決するには、UDT の定義の後にその UDT を返す関数を宣言します。  
  
```cpp  
// C2440b.cpp  
struct MyStruct;  
  
MyStruct get_c1();  
  
struct MyStruct {  
   int i;  
   static MyStruct get_C2();  
};  
  
MyStruct get_C3();  
  
typedef MyStruct (*FC)();  
  
FC fc1 = &get_c1;   // C2440, line 15  
FC fc2 = &MyStruct::get_C2;   // C2440, line 16  
FC fc3 = &get_C3;  
  
class CMyClass {  
public:  
   explicit CMyClass( int iBar)  
      throw()   {  
   }  
  
   static CMyClass get_c2();  
};  
  
int main() {  
   CMyClass myclass = 2;   // C2440  
   // try one of the following  
   // CMyClass myclass{2};  
   // CMyClass myclass(2);  
  
   int *i;  
   float j;  
   j = (float)i;   // C2440, cannot cast from pointer to int to float  
}  
```  
  
## 使用例  
 C2440 は、内部ポインターに 0 を割り当てた場合にも発生することがあります。  
  
```cpp  
// C2440c.cpp  
// compile with: /clr  
int main() {  
   array<int>^ arr = gcnew array<int>(100);  
   interior_ptr<int> ipi = &arr[0];  
   ipi = 0;   // C2440  
   ipi = nullptr;   // OK  
}  
```  
  
## 使用例  
 C2440 は、ユーザー定義の規約の使用方法が間違っている場合にも発生することがあります。  ユーザー定義の規約の詳細については、「[ユーザー定義変換](../../dotnet/user-defined-conversions-cpp-cli.md)」を参照してください。  次の例では C2440 エラーが生成されます。  
  
```cpp  
// C2440d.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
   // convert MyDouble to Int32  
   static explicit operator System::Int32 ( MyDouble val ) {  
      return (int)val.d;  
   }  
};  
  
int main() {  
   MyDouble d;  
   int i;  
   i = d;   // C2440  
   // Uncomment the following line to resolve.  
   // i = static_cast<int>(d);  
}  
```  
  
## 使用例  
 C2440 は、型が <xref:System.Array> である Visual C\+\+ 配列のインスタンスを作成しようとした場合にも発生することがあります。詳細については、「[Arrays](../../windows/arrays-cpp-component-extensions.md)」を参照してください。次の例では C2440 が生成されます。  
  
```cpp  
// C2440e.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   array<int>^ intArray = Array::CreateInstance(__typeof(int), 1);   // C2440  
   // try the following line instead  
   // array<int>^ intArray = safe_cast<array<int> ^>(Array::CreateInstance(__typeof(int), 1));  
}  
```  
  
## 使用例  
 C2440 は、属性機能の変更が原因で発生することもあります。次の例では C2440 エラーが生成されます。  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## 使用例  
 Visual C\+\+ コンパイラは、**\/clr** プログラミングを使用するソース コードをコンパイルするときに [const\_cast 演算子](../Topic/const_cast%20Operator.md) のダウン キャストを許可しなくなりました。  
  
 この C2440 エラーを解決するには、正しいキャスト演算子を使用します。  詳細については、「[キャスト演算子](../../cpp/casting-operators.md)」を参照してください。  
  
 次の例では C2440 エラーが生成されます。  
  
```cpp  
// c2440g.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
int main() {  
   Derived ^d = gcnew Derived;  
   Base ^b = d;  
   d = const_cast<Derived^>(b);   // C2440  
   d = dynamic_cast<Derived^>(b);   // OK  
}  
```  
  
## 使用例  
 C2440 は **\/clr:oldSyntax** の使用によって生成されることもあります。  
  
```cpp  
// c2440h.cpp  
// compile with: /clr:oldSyntax  
__gc class Base {};  
__gc class Derived : public Base {};  
int main() {  
   Derived *d = new Derived;  
   Base *b = d;  
   d = const_cast<Derived*>(b);   // C2440  
   d = dynamic_cast<Derived*>(b);   // OK  
}  
```