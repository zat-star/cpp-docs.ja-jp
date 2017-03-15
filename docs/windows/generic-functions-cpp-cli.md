---
title: "Generic Functions (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "functions [C++], generic"
  - "generic methods"
  - "generics [C++], functions"
  - "methods [C++], generic"
  - "generic functions"
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
caps.latest.revision: 21
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Functions (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ジェネリック関数は型パラメーターとして宣言した関数です。  呼び出されたときに、実際の型パラメーターの代わりに使用されます。  
  
## すべてのプラットフォーム  
 **解説**  
  
 この機能は、すべてのプラットフォームには適用されません。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **解説**  
  
 この機能は [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]ではサポートされていません。  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 ジェネリック関数は型パラメーターとして宣言した関数です。  呼び出されたときに、実際の型パラメーターの代わりに使用されます。  
  
 **構文**  
  
```  
[attributes] [modifiers]  
return-type identifier <type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{  
   function-body  
}  
```  
  
 **パラメーター**  
  
 *attributes* \(省略可能\)  
 追加の宣言情報。  属性と属性クラスの詳細については、属性を参照します。  
  
 *modifiers* \(省略可能な\)  
 atic stなどの関数の修飾子。`virtual` は仮想メソッドはジェネリックではない場合があるため、使用できません。  
  
 *return\-type*  
 メソッドによって返される型。  戻り値の型が void の場合、戻り値は必要ではありません。  
  
 *identifier*  
 関数名。  
  
 *type\-parameter identifier\(s\)*  
 コンマで区切られた ID のリスト。  
  
 *formal\-parameters* \(省略可能\)  
 パラメーター リストを指定します。  
  
 *type\-parameter\-constraints\-clauses*  
 これは、型引数として使用できる指定し [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../Topic/Constraints%20on%20Generic%20Type%20Parameters%20\(C++-CLI\).md)で指定された形式になります。型に制限を適用します。  
  
 *function\-body*  
 型パラメーターの ID を示す、メソッドの本体。  
  
 **解説**  
  
 ジェネリック関数はジェネリック型パラメーターとして宣言した関数です。  そのクラスまたは構造体のメソッド、またはスタンドアロン関数である可能性があります。  暗黙的な単一のジェネリック宣言はジェネリック型パラメーターの実際の型の代替だけで異なるファミリの関数を宣言します。  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]で、クラスまたは構造体コンストラクターはジェネリック型パラメーターで宣言されていない可能性があります。  
  
 このメソッドを呼び出すと、ジェネリック型パラメーターは実際の型に置き換えられます。  実際の型はテンプレート関数の呼び出しに似た構文を使用してかぎカッコに明示的に指定される場合があります。  型パラメーターなしであった場合、関数呼び出しに指定されたパラメーターの実際の型を推論しようとします。  目的の型の引数を使用したパラメーターから推測できない場合は、コンパイラがエラーを報告します。  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 次のコード サンプルはジェネリック関数を示します。  
  
```  
// generics_generic_function_1.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
ref struct A {  
   generic <typename ItemType>  
   void G(ItemType) {}  
  
   generic <typename ItemType>  
   static void H(int i) {}  
};  
  
int main() {  
   A myObject;  
  
   // generic function call  
   myObject.G<int>(10);  
  
   // generic function call with type parameters deduced  
   myObject.G(10);  
  
   // static generic function call  
   A::H<int>(10);  
  
   // global generic function call  
   G<int>(10);  
}  
```  
  
 **例**  
  
 ジェネリック関数はシグネチャまたはアリティ関数の型パラメーターの数に基づいてオーバーロードすることができます。  また、ジェネリック関数は同じ名前の非ジェネリック関数と関数がある型パラメーターで異なる限りオーバーロードすることができます。  たとえば、次の関数はオーバーロードすることがあります:  
  
```  
// generics_generic_function_2.cpp  
// compile with: /clr /c  
ref struct MyClass {  
   void MyMythod(int i) {}  
  
   generic <class T>   
   void MyMythod(int i) {}  
  
   generic <class T, class V>   
   void MyMythod(int i) {}  
};  
```  
  
 **例**  
  
 次の例では、配列の最初の要素を検索するためにジェネリック関数を使用します。  基本クラス `MyBaseClass`から継承する場合は `MyClass`を宣言します。  `MyClass` は 別のジェネリック関数を呼び出すジェネリック関数、`MyFunction`の、基本クラス内の `MyBaseClassFunction`も含まれます。  **main**で、ジェネリック関数、`MyFunction`に異なる型の引数を使用して呼び出します。  
  
```  
// generics_generic_function_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyBaseClass {  
protected:  
   generic <class ItemType>  
   ItemType MyBaseClassFunction(ItemType item) {  
      return item;  
   }  
};  
  
ref class MyClass: public MyBaseClass {  
public:  
   generic <class ItemType>  
   ItemType MyFunction(ItemType item) {  
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);  
   }  
};  
  
int main() {  
   MyClass^ myObj = gcnew MyClass();  
  
   // Call MyFunction using an int.  
   Console::WriteLine("My function returned an int: {0}",  
                           myObj->MyFunction<int>(2003));  
  
   // Call MyFunction using a string.  
   Console::WriteLine("My function returned a string: {0}",  
   myObj->MyFunction<String^>("Hello generic functions!"));  
}  
```  
  
 **出力**  
  
  **次の関数は、int を返しました: 2003 年**  
 **次の関数は、文字列が返されました: Hello ジェネリック関数\!**   
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Generics](../windows/generics-cpp-component-extensions.md)