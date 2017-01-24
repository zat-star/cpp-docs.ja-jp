---
title: "attribute | Microsoft Docs"
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
  - "vc-attr.attribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__typeof keyword"
  - "custom attributes, creating"
  - "attribute attribute"
  - "attributes [C++], custom"
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# attribute
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

カスタム属性を作成する。  
  
## 構文  
  
```  
  
      [ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### パラメーター  
 *AllowOn*  
 カスタム属性を適用できる言語要素を指定します。  既定値はです **System::AttributeTargets:: すべて**  \([System:: AttributeTargets](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx) を参照してください。  
  
 `AllowMultiple`  
 カスタム属性は構造体に繰り返し適用できるかどうかを指定します。  既定値は **False** です。  
  
 `Inherited`  
 属性がサブクラスに継承するかどうかを示します。  コンパイラではこの機能を特別にサポートしていません ; これはこの情報を考慮する属性の使用 \(リフレクションなど\) のジョブがあります。  `Inherited` が **True** 場合この属性によって継承されます。  `AllowMultiple` が **True** した場合この属性は派生メンバーに蓄積 ; `AllowMultiple` が **False** の場合属性が適用されます \(または置換\) をオーバーライドします。  `Inherited` が **False** した場合この属性は継承されません。  既定値は **True** です。  
  
## 解説  
  
> [!NOTE]
>  `attribute` の属性は使用されていません。  ユーザー定義の attirbutes を作成するには直接に共通言語ランタイム \(CLR System.Attribute 属性を使用します。  詳細については、「[User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。  
  
 マネージ クラスまたは構造体の定義に `attribute` の属性を設定して [カスタム属性](../windows/custom-attributes-cpp.md) を定義します。  カスタム属性クラスの名前はです。  次に例を示します。  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 関数パラメーターに適用できる MyAttr という属性を定義します。  クラスは属性を他のアセンブリで使用されている場合はパブリックである必要があります。  
  
> [!NOTE]
>  名前空間の競合を回避するには属性名は 「 Attribute 」で暗黙的に exit; この例では属性の名前およびクラスは実際に MyAttrAttribute がMyAttr と MyAttrAttribute は交換して使用できます。  
  
 クラスのパブリック コンストラクターが属性の無名のパラメーターを定義します。  オーバーロードされたコンストラクターでは属性は次の方法で定義されたカスタム属性を指定するいくつかの方法を使用する :  
  
```  
// cpp_attr_ref_attribute.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]   // apply attribute to classes  
public ref class MyAttr {  
public:  
   MyAttr() {}   // Constructor with no parameters  
   MyAttr(int arg1) {}   // Constructor with one parameter  
};  
  
[MyAttr]  
ref class ClassA {};   // Attribute with no parameters  
  
[MyAttr(123)]  
ref class ClassB {};   // Attribute with one parameter  
```  
  
 クラスのパブリック データ メンバーとプロパティは属性を省略できる名前付きパラメーターです :  
  
```  
// cpp_attr_ref_attribute_2.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]  
ref class MyAttr {  
public:  
   // Property Priority becomes attribute's named parameter Priority  
    property int Priority {  
       void set(int value) {}  
       int get() { return 0;}  
   }  
   // Data member Version becomes attribute's named parameter Version  
   int Version;  
   MyAttr() {}   // constructor with no parameters  
   MyAttr(int arg1) {}   // constructor with one parameter  
};  
  
[MyAttr(123, Version=2)]   
ref class ClassC {};  
```  
  
 使用可能な属性のパラメーターの一覧については[カスタム属性](../windows/custom-attributes-cpp.md) を参照してください。  
  
 属性ターゲットの詳細については[User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md) を参照してください。  
  
 `attribute` の属性にカスタム属性は単一の使用または使ってかどうかを指定する `AllowMultiple` のパラメーターがあります \(同じエンティティ内で複数回使用できます\)。  
  
```  
// cpp_attr_ref_attribute_3.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class, AllowMultiple = true) ]  
ref struct MyAttr {  
   MyAttr(){}  
};   // MyAttr is a multiuse attribute  
  
[MyAttr, MyAttr()]  
ref class ClassA {};  
```  
  
 カスタム属性クラスは <xref:System.ComponentModel.AttributeCollection.%23ctor%2A> から直接または間接的に派生しているメタデータの中で属性の定義を高速で簡単になります。  `attribute` の属性はシステムからの継承を意味します :: 属性ため明示派生は不要です :  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 上記のコードは、次のコードと同じです。  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute` <xref:System.AttributeUsageAttribute?displayProperty=fullName> はなく AttributeAttribute のエイリアスです ; これにより属性の名前付け規則には例外です\)。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`ref`  **クラス ref の構造体**|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 使用例  
  
```  
// cpp_attr_ref_attribute_4.cpp  
// compile with: /c /clr  
using namespace System;  
[attribute(AttributeTargets::Class)]  
ref struct ABC {  
   ABC(Type ^) {}  
};  
  
[ABC(String::typeid)]   // typeid operator yields System::Type ^  
ref class MyClass {};  
```  
  
## 使用例  
 `Inherited` の名前付き引数は基本クラスに適用されたカスタム属性の派生クラスでリフレクションに表示されるかどうかを指定します。  
  
```  
// cpp_attr_ref_attribute_5.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
[attribute( AttributeTargets::Method, Inherited=false )]  
ref class BaseOnlyAttribute { };  
  
[attribute( AttributeTargets::Method, Inherited=true )]  
ref class DerivedTooAttribute { };  
  
ref struct IBase {  
public:  
   [BaseOnly, DerivedToo]  
   virtual void meth() {}  
};  
  
// Reflection on Derived::meth will show DerivedTooAttribute   
// but not BaseOnlyAttribute.  
ref class Derived : public IBase {  
public:  
   virtual void meth() override {}  
};  
  
int main() {  
   IBase ^ pIB = gcnew Derived;  
  
   MemberInfo ^ pMI = pIB->GetType( )->GetMethod( "meth" );  
   array<Object ^> ^ pObjs = pMI->GetCustomAttributes( true );  
   Console::WriteLine( pObjs->Length ) ;  
}  
```  
  
  **2**   
## 参照  
 [Attributes Alphabetical Reference](../windows/attributes-alphabetical-reference.md)   
 [Custom Attributes](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)