---
title: "interface class  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "interface_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interface class keyword"
  - "interface struct keyword"
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
caps.latest.revision: 30
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# interface class  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インターフェイスを宣言します。ネイティブ インターフェイスの詳細については、「[\_\_interface](../Topic/__interface.md)」を参照してください。  
  
## すべてのランタイム  
 **構文**  
  
```  
  
        interface_access interface class  name :  inherit_access base_interface {};  
interface_access interface struct name :  inherit_access base_interface {};  
```  
  
 **パラメーター**  
  
 *interface\_access*  
 アセンブリの外部でインターフェイスのアクセシビリティを確認します。有効値は **パブリック** と `private`です。`private` は既定です。入れ子になったインターフェイスは *interface\_access* の指定子を含めることはできません。  
  
 *name*  
 インターフェイスの名前。  
  
 *inherit\_access*  
 *base\_interface* のアクセシビリティ。基本インターフェイスの唯一の許可されたアクセシビリティは `public` \(既定\) です。  
  
 *base\_interface* \(省略可能\)  
 インターフェイス *name*の基本インターフェイス。  
  
 **解説**  
  
 **インターフェイス構造体** は **インターフェイス クラス**と同じです。  
  
 インターフェイスは、関数、イベント、およびプロパティの宣言を含めることができます。すべてのインターフェイス メンバーにはパブリックなアクセシビリティがあります。  インターフェイスは、静的データ メンバー、関数、イベント、およびプロパティを含めることができ、それらの静的メンバーがインターフェイスで定義する必要があります。  
  
 インターフェイスはクラスがどのように実装される可能性があるかを定義します。  インターフェイスはクラスではなく、クラスはインターフェイスの実装だけです。  クラスがインターフェイスで宣言された関数を定義する場合、関数は実装されましたり、オーバーライドされません。  したがって、名前の参照は、インターフェイス メンバーは含まれません。  
  
 インターフェイスから派生するクラスまたは構造体は、インターフェイスのすべてのメンバーを実装しなければなりません。  インターフェイス名を実装したときにも表示されます `base_interface` のインターフェイスを実装しなければなりません。  
  
 詳細については、次のトピックを参照してください。  
  
-   [インターフェイス静的コンストラクター](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [Generic Interfaces \(Visual C\+\+\)](../Topic/Generic%20Interfaces%20\(Visual%20C++\).md)  
  
 他の CLR 型の詳細については、「[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。  
  
 型が `__is_interface_class(``type``)`のインターフェイスかどうかコンパイル時に検出できます。  詳細については、「[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)」を参照してください。  
  
 開発環境では、キーワード \(`interface class` など\) 選択して F1 キーを押すことで、そのキーワードに関する F1 ヘルプを表示できます。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **解説**  
  
 \(この言語機能には Windows ランタイムのみに適用される特記事項がありません。\)  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **解説**  
  
 \(この言語機能には共通言語ランタイムのみに適用される特記事項がありません。\)  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 次のコード例にインターフェイスが clock 関数の動作を定義する方法を示します。  
  
```  
// mcppv2_interface_class.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void ClickEventHandler(int, double);  
  
// define interface with nested interface  
public interface class Interface_A {  
   void Function_1();  
  
   interface class Interface_Nested_A {  
      void Function_2();  
   };  
};  
  
// interface with a base interface  
public interface class Interface_B : Interface_A {  
   property int Property_Block;  
   event ClickEventHandler^ OnClick;     
   static void Function_3() { Console::WriteLine("in Function_3"); }  
};  
  
// implement nested interface  
public ref class MyClass : public Interface_A::Interface_Nested_A {  
public:  
   virtual void Function_2() { Console::WriteLine("in Function_2"); }  
};  
  
// implement interface and base interface  
public ref class MyClass2 : public Interface_B {  
private:  
   int MyInt;  
  
public:  
   // implement non-static function  
   virtual void Function_1() { Console::WriteLine("in Function_1"); }  
  
   // implement property  
   property int Property_Block {  
      virtual int get() { return MyInt; }  
      virtual void set(int value) { MyInt = value; }  
   }  
   // implement event  
   virtual event ClickEventHandler^ OnClick;  
  
   void FireEvents() {  
      OnClick(7, 3.14159);  
   }  
};  
  
// class that defines method called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
};  
  
int main() {  
   // call static function in an interface  
   Interface_B::Function_3();  
  
   // instantiate class that implements nested interface  
   MyClass ^ x = gcnew MyClass;  
   x->Function_2();  
  
   // instantiate class that implements interface with base interface  
   MyClass2 ^ y = gcnew MyClass2;  
   y->Function_1();  
   y->Property_Block = 8;  
   Console::WriteLine(y->Property_Block);  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   y->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // invoke events  
   y->FireEvents();  
  
   // unhook handler to event  
   y->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // call implemented function via interface handle  
   Interface_A^ hi = gcnew MyClass2();  
   hi->Function_1();  
}  
```  
  
 **出力**  
  
  **Function\_3**  
 **Function\_2**  
 **Function\_1**  
 **8**  
 **OnClick: 7, 3.14159**  
 **Function\_1** **例**  
  
 次のコード サンプルでは、これらのインターフェイスをクラスによって使用される場所で複数のインターフェイスで宣言されている同じシグネチャを持つ関数を実装するには、2 とおりの方法を示します。  
  
```  
// mcppv2_interface_class_2.cpp  
// compile with: /clr /c  
interface class I {  
   void Test();  
   void Test2();  
};  
  
interface class J : I {  
   void Test();  
   void Test2();  
};  
  
ref struct R : I, J {  
   // satisfies the requirement to implement Test in both interfaces  
   virtual void Test() {}  
  
   // implement both interface functions with explicit overrides  
   virtual void A() = I::Test2 {}  
   virtual void B() = J::Test2 {}  
};  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)