---
title: "方法: C++/CLI でプロパティを使用する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プロパティ [C++], 単純な"
  - "単純プロパティ"
ms.assetid: f5d82547-e214-4f05-9e1b-ddb6d0dc5e4c
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: C++/CLI でプロパティを使用する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは C\+\+\/CLI でプロパティを使用する方法を示します。  
  
## 基本的なプロパティ  
 これらの基本プロパティに対して、プロパティのデータ型が指定されている場合、コンパイラが自動的に提供されるため、プライベート データ メンバーを割り当て、取得する get および set アクセサー関数を明示的に定義する必要はありません。  このコードは、基本的なプロパティを持つ T:  
  
```  
// SimpleProperties.cpp  
// compile with: /clr  
using namespace System;  
  
ref class C {  
public:  
   property int Size;  
};  
  
int main() {  
   C^ c = gcnew C;  
   c->Size = 111;  
   Console::WriteLine("c->Size = {0}", c->Size);  
}  
```  
  
 **出力**  
  
  **c サイズ\>\= 111**   
## 静的プロパティ  
 このコード サンプルは静的プロパティを宣言して使用する方法を示します。静的プロパティは、クラスの静的メンバーだけにアクセスできます。  
  
```  
// mcppv2_property_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class StaticProperties {  
   static int MyInt;  
   static int MyInt2;  
  
public:  
   static property int Static_Data_Member_Property;  
  
   static property int Static_Block_Property {  
      int get() {  
         return MyInt;  
      }  
  
      void set(int value) {  
         MyInt = value;  
      }        
   }  
};  
  
int main() {  
   StaticProperties::Static_Data_Member_Property = 96;  
   Console::WriteLine(StaticProperties::Static_Data_Member_Property);  
  
   StaticProperties::Static_Block_Property = 47;  
   Console::WriteLine(StaticProperties::Static_Block_Property);  
}  
```  
  
 **出力**  
  
  **96**  
**47**   
## インデックス付きプロパティ  
 インデックス付きプロパティは、添字演算子を使用してアクセスするデータ構造を公開します。  
  
 既定のインデックス付きプロパティを使用する場合は、クラス名の参照によってデータ構造体にアクセスできます。ユーザー定義のインデックス付きプロパティを使用すると、データ構造にアクセスするためのプロパティ名を指定する必要があります。  
  
 `this` のポインターを使用して既定のインデクサーにアクセスする方法の詳細については、「[値型および参照型における this ポインターのセマンティクス](../misc/semantics-of-the-this-pointer-in-value-and-reference-types.md)」を参照してください。  
  
 C\# で記述されたインデクサーを使用する方法の詳細については、「[方法: C\# インデクサーを使用する](../dotnet/how-to-consume-a-csharp-indexer-cpp-cli.md)」を参照してください。  
  
 このコード サンプルが既定とユーザー定義のインデックス付きプロパティの使用例を:  
  
```  
// mcppv2_property_2.cpp  
// compile with: /clr  
using namespace System;  
public ref class C {  
   array<int>^ MyArr;  
  
public:  
   C() {  
      MyArr = gcnew array<int>(5);  
   }  
  
   // default indexer  
   property int default[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
  
   // user-defined indexer  
   property int indexer1[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
};  
  
int main() {  
   C ^ MyC = gcnew C();  
  
   // use the default indexer  
   Console::Write("[ ");  
   for (int i = 0 ; i < 5 ; i++) {  
      MyC[i] = i;  
      Console::Write("{0} ", MyC[i]);  
   }  
  
   Console::WriteLine("]");  
  
   // use the user-defined indexer  
   Console::Write("[ ");  
   for (int i = 0 ; i < 5 ; i++) {  
      MyC->indexer1[i] = i * 2;  
      Console::Write("{0} ", MyC->indexer1[i]);  
   }  
  
   Console::WriteLine("]");  
}  
```  
  
 **出力**  
  
  **\[ 0 1 2 3 4 \]**  
**\[ 0 2 4 6 8 \]** 次の例では `this` のポインターを使用して既定のインデクサーを呼び出す方法を示します。  
  
```  
// call_default_indexer_through_this_pointer.cpp  
// compile with: /clr /c  
value class Position {  
public:  
   Position(int x, int y) : position(gcnew array<int, 2>(100, 100)) {  
      this->default[x, y] = 1;  
   }  
  
   property int default[int, int] {  
      int get(int x, int y) {  
         return position[x, y];  
      }  
  
      void set(int x, int y, int value) {}  
   }  
  
private:  
   array<int, 2> ^ position;  
};  
```  
  
 このサンプルでは、既定のインデクサーを指定するために <xref:System.Reflection.DefaultMemberAttribute> を使用する方法について説明します。:  
  
```  
// specify_default_indexer.cpp  
// compile with: /LD /clr  
using namespace System;  
[Reflection::DefaultMember("XXX")]  
public ref struct Squares {  
   property Double XXX[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
```  
  
 前の例で作成した次の例は、メタデータを使用します。  
  
```  
// consume_default_indexer.cpp  
// compile with: /clr  
#using "specify_default_indexer.dll"  
int main() {  
   Squares ^ square = gcnew Squares();  
   System::Console::WriteLine("{0}", square[3]);  
}  
```  
  
 **出力**  
  
 **9**   
## 仮想プロパティ  
 このコード サンプルでは、仮想プロパティの宣言と使用方法を説明します:  
  
```  
// mcppv2_property_4.cpp  
// compile with: /clr  
using namespace System;  
interface struct IEFace {  
public:  
   property int VirtualProperty1;  
   property int VirtualProperty2 {  
      int get();  
      void set(int i);  
   }  
};  
  
// implement virtual events  
ref class PropImpl : public IEFace {  
   int MyInt;  
public:  
   virtual property int VirtualProperty1;  
  
   virtual property int VirtualProperty2 {  
      int get() {  
         return MyInt;  
      }  
      void set(int i) {  
         MyInt = i;  
      }  
   }  
};  
  
int main() {  
   PropImpl ^ MyPI = gcnew PropImpl();  
   MyPI->VirtualProperty1 = 93;  
   Console::WriteLine(MyPI->VirtualProperty1);  
  
   MyPI->VirtualProperty2 = 43;  
   Console::WriteLine(MyPI->VirtualProperty2);  
}  
```  
  
 **出力**  
  
  **93**  
**43**   
## abstract、sealed プロパティ  
 、Visual C\+\+ コンパイラ用の ECMA C\+\+\/CLI 仕様で有効に [abstract](../windows/abstract-cpp-component-extensions.md) と [sealed](../windows/sealed-cpp-component-extensions.md) キーワードが指定されていますが、単純なプロパティで、重要なプロパティのプロパティ宣言でそれらを指定できません。  
  
 シールされているか、または抽象プロパティを宣言するには、重要なプロパティを定義し、get アクセサーと set アクセサーの関数で `abstract` または `sealed` キーワードを指定する必要があります。  
  
```  
// properties_abstract_sealed.cpp  
// compile with: /clr  
ref struct A {  
protected:  
   int m_i;  
  
public:  
   A() { m_i = 87; }  
  
   // define abstract property  
   property int Prop_1 {  
      virtual int get() abstract;  
      virtual void set(int i) abstract;  
   }  
};  
  
ref struct B : A {  
private:  
   int m_i;  
  
public:  
   B() { m_i = 86; }  
  
   // implement abstract property  
   property int Prop_1 {  
      virtual int get() override { return m_i; }  
      virtual void set(int i) override { m_i = i; }  
   }  
};  
  
ref struct C {  
private:  
   int m_i;  
  
public:  
   C() { m_i = 87; }  
  
   // define sealed property  
   property int Prop_2 {  
      virtual int get() sealed { return m_i; }  
      virtual void set(int i) sealed { m_i = i; };  
   }  
};  
  
int main() {  
   B b1;  
   // call implementation of abstract property  
   System::Console::WriteLine(b1.Prop_1);  
  
   C c1;  
   // call sealed property  
   System::Console::WriteLine(c1.Prop_2);  
}  
```  
  
 **出力**  
  
  **86**  
**87**   
## 多次元プロパティ  
 パラメーターの標準以外の数を受け取るプロパティのアクセサー メソッドを定義するには、多次元プロパティを使用できます。  
  
```  
// mcppv2_property_5.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(0) {}  
   property double MultiDimProp[int, int, int] {  
      double get(int, int, int) {  
         return d;  
      }  
      void set(int i, int j, int k, double l) {  
         // do something with those ints  
         d = l;  
      }  
   }  
  
   property double MultiDimProp2[int] {  
      double get(int) {  
         return d;  
      }  
      void set(int i, double l) {  
         // do something with those ints  
         d = l;  
      }  
   }  
  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   MyX->MultiDimProp[0,0,0] = 1.1;  
   System::Console::WriteLine(MyX->MultiDimProp[0, 0, 0]);  
}  
```  
  
 **出力**  
  
  **1.1**   
## プロパティ アクセサーのオーバーロード  
 次の例は、インデックス付きプロパティをオーバーロードする方法を示します。  
  
```  
// mcppv2_property_6.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(0.0) {}  
   property double MyProp[int] {  
      double get(int i) {  
         return d;  
      }  
  
      double get(System::String ^ i) {  
         return 2*d;  
      }  
  
      void set(int i, double l) {  
         d = i * l;  
      }  
   }   // end MyProp definition  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   MyX->MyProp[2] = 1.7;  
   System::Console::WriteLine(MyX->MyProp[1]);  
   System::Console::WriteLine(MyX->MyProp["test"]);  
}  
```  
  
 **出力**  
  
  **3.4**  
**6.8**   
## 参照  
 [property](../windows/property-cpp-component-extensions.md)