---
title: "User-Defined Attributes  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "metadata, extending"
  - "custom attributes, extending metadata"
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# User-Defined Attributes  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

カスタム属性を使用すると、インターフェイスのメタデータが、クラス、構造体、メソッド、パラメーター、または列挙体拡張できます。  
  
## すべてのランタイム  
 すべてのランタイム サポート カスタム属性。  
  
## Windows ランタイム  
 C\+\+\/CX 属性サポート プロパティのみが、属性コンストラクターまたはメソッド。  
  
### 解説  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## 共通言語ランタイム  
 カスタム属性は、マネージ要素のメタデータを拡張することができます。  詳細については、「[属性](../Topic/Extending%20Metadata%20Using%20Attributes.md)」を参照してください。  
  
### 解説  
 このトピックに示す情報と構文が [attribute](../windows/attribute.md)で提供される情報により優先されるようになっています。  
  
 型を定義し、<xref:System.Attribute> に型の基本クラスをでき、オプションで <xref:System.AttributeUsageAttribute> 属性を適用することにより、カスタム属性を定義することもできます。  
  
 たとえば、Microsoft Transaction Server \(MTS\) で 1.0 トランザクションに関する動作、同期、負荷分散 ODL などのカスタム属性を使用してタイプ ライブラリに挿入されたカスタム GUID で指定されました。  したがって、MTS サーバーのクライアントはタイプ ライブラリを読み込むことによって特性を確認できます。  .NET Framework では、タイプ ライブラリのように、メタデータであり、ODL のカスタム属性のようにカスタム属性です。  また、タイプ ライブラリを読み込む方法は型のリフレクション操作に似ています。  
  
 詳細については、次のトピックを参照してください。  
  
-   [Attribute Targets](../windows/attribute-targets-cpp-component-extensions.md)  
  
-   [Attribute Parameter Types](../windows/attribute-parameter-types-cpp-component-extensions.md)  
  
 Visual C\+\+ のアセンブリの署名の詳細については、「[厳密名アセンブリ \(アセンブリ署名\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)」を参照してください。  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 次の例では、カスタム属性を定義する方法を示します。  
  
```cpp  
// user_defined_attributes.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
ref struct Attr : public Attribute {  
   Attr(bool i){}  
   Attr(){}  
};  
  
[Attr]  
ref class MyClass {};  
```  
  
 **例**  
  
 次の例では、カスタム属性の主な機能を示しています。  たとえば、この例では、カスタム属性の一般的な使用方法を示しています。: クライアントに十分に記述できるサーバーをインスタンス化します。  
  
```cpp  
// extending_metadata_b.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
public enum class Access { Read, Write, Execute };  
  
// Defining the Job attribute:  
[AttributeUsage(AttributeTargets::Class, AllowMultiple=true )]  
public ref class Job : Attribute {  
public:  
   property int Priority {  
      void set( int value ) { m_Priority = value; }  
      int get() { return m_Priority; }  
   }  
  
   // You can overload constructors to specify Job attribute in different ways  
   Job() { m_Access = Access::Read; }  
   Job( Access a ) { m_Access = a; }  
   Access m_Access;  
  
protected:  
   int m_Priority;  
};  
  
interface struct IService {  
   void Run();  
};  
  
   // Using the Job attribute:  
   // Here we specify that QueryService is to be read only with a priority of 2.  
   // To prevent namespace collisions, all custom attributes implicitly   
   // end with "Attribute".   
  
[Job( Access::Read, Priority=2 )]  
ref struct QueryService : public IService {  
   virtual void Run() {}  
};  
  
// Because we said AllowMultiple=true, we can add multiple attributes   
[Job(Access::Read, Priority=1)]  
[Job(Access::Write, Priority=3)]  
ref struct StatsGenerator : public IService {  
   virtual void Run( ) {}  
};  
  
int main() {  
   IService ^ pIS;  
   QueryService ^ pQS = gcnew QueryService;  
   StatsGenerator ^ pSG = gcnew StatsGenerator;  
  
   //  use QueryService  
   pIS = safe_cast<IService ^>( pQS );  
  
   // use StatsGenerator  
   pIS = safe_cast<IService ^>( pSG );  
  
   // Reflection  
   MemberInfo ^ pMI = pIS->GetType();  
   array <Object ^ > ^ pObjs = pMI->GetCustomAttributes(false);  
  
   // We can now quickly and easily view custom attributes for an   
   // Object through Reflection */  
   for( int i = 0; i < pObjs->Length; i++ ) {  
      Console::Write("Service Priority = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->Priority);  
      Console::Write("Service Access = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->m_Access);  
   }  
}  
```  
  
 **出力**  
  
  **優先度 \= 0 を処理します。**  
 **サービス アクセス \= 書き込みます**  
 **優先度 \= 3 を処理します。**  
 **サービス アクセス \= 書き込みます**  
 **優先度 \= 1 を処理します。**  
 **\= 読み取りアクセスを提供します。** **例**  
  
 Object^ の型はバリアント型を置き換えます。  次の例では、パラメーターとして Object^ の配列を指定するカスタム属性を定義しています。  
  
 属性引数は、コンパイル時の定数である; ほとんどの場合、定数リテラル。  
  
 カスタム属性ブロックから System::Type の値を返す方法については、" [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) を参照してください。  
  
```cpp  
// extending_metadata_e.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Method)]  
public ref class AnotherAttr : public Attribute {  
public:  
   AnotherAttr(array<Object^>^) {}  
   array<Object^>^ var1;  
};  
  
// applying the attribute  
[ AnotherAttr( gcnew array<Object ^> { 3.14159, "pi" }, var1 = gcnew array<Object ^> { "a", "b" } ) ]  
public ref class SomeClass {};  
```  
  
 **例**  
  
 ランタイムはカスタム属性クラスのパブリックな部分にシリアル化する必要があります。カスタム属性を作成すると、カスタム属性の名前付き引数は、コンパイル定数だけです。メタデータのクラスのレイアウトに付けられたビットのシーケンスであることに注意してください\)。  
  
```cpp  
// extending_metadata_f.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct abc {};  
  
[AttributeUsage( AttributeTargets::All )]  
ref struct A : Attribute {  
   A( Type^ ) {}  
   A( String ^ ) {}  
   A( int ) {}  
};  
  
[A( abc::typeid )]  
ref struct B {};  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)