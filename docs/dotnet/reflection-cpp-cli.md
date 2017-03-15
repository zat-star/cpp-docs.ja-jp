---
title: "リフレクション (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - ".NET Framework [C++], リフレクション"
  - "データ型 [C++], リフレクション"
  - "GetType メソッド"
  - "メタデータ, リフレクション"
  - "リフレクション [C++]"
  - "リフレクション [C++], リフレクションの概要"
  - "typeid キーワード [C++]"
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リフレクション (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リフレクションでは、既知のデータ型を実行時に調査できます。  リフレクションでは、アセンブリに含まれているデータ型を列挙したり、クラス型や値型のメンバーを探索したりできます。  この処理は、コンパイル時に型が認識または参照された場合のどちらにも対応できます。  そのため、リフレクションは、開発およびコード管理ツール向けの便利な機能です。  
  
 出力されたアセンブリ名は、アセンブリのバージョン、カルチャ、および署名情報が含まれた厳密な名前です。詳細については、「[厳密な名前付きアセンブリの作成と使用](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)」を参照してください。  また、基底クラスの名前に加えて、データ型が定義されている名前空間の名前も取得できることに注目してください。  
  
 リフレクションの機能にアクセスする最も一般的な方法は、<xref:System.Object.GetType%2A> メソッドを使用することです。  このメソッドは、すべてのガベージ コレクション クラスの派生元である [System::Object](https://msdn.microsoft.com/en-us/library/system.object.aspx) に用意されています。  
  
 Visual C\+\+ コンパイラで構築された .exe の場合、その .exe が **\/clr:pure** または **\/clr:safe** コンパイラ オプションを使用して構築されていれば、リフレクションを使用できます。  詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 このセクションのトピック  
  
-   [方法: リフレクションを使用してプラグイン コンポーネント アーキテクチャを実装する](../dotnet/how-to-implement-a-plug-in-component-architecture-using-reflection-cpp-cli.md)  
  
-   [方法: リフレクションを使用してアセンブリ内のデータ型を列挙する](../dotnet/how-to-enumerate-data-types-in-assemblies-using-reflection-cpp-cli.md)  
  
 詳細については、「[System.Reflection 名前空間](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)」を参照してください。  
  
## 使用例  
 `GetType` メソッドは、オブジェクトが基になっている場合は型を表す <xref:System.Type> クラス オブジェクトへのポインターを返します。**Type** オブジェクトには、インスタンス固有の情報は含まれていません。このメソッドで取得できる項目には、型の完全名があります。完全名は、次のように表示できます。  
  
 型名には、型が定義されている完全なスコープ \(名前空間も含む\) が含まれています。また、.NET 構文でスコープ解決演算子としてドット \(.\) が付けられている点にも注意してください。  
  
```  
// vcpp_reflection.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
```  
  
  **full type name of 'sample string' is 'System.String'**   
## 使用例  
 値型を `GetType` 関数で使用する場合も、最初にボックス化する必要があります。  
  
```  
// vcpp_reflection_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Int32 i = 100;   
   Object ^ o = i;  
   Console::WriteLine("type of i = '{0}'", o->GetType());  
}  
```  
  
  **type of i \= 'System.Int32'**   
## 使用例  
 `GetType` メソッドの場合と同様、[typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) 演算子は **Type** オブジェクトへのポインターを返します。したがって、このコードでは **System.Int32** という型名を指定します。  型名を表示することは、リフレクションの最も基本的な機能ですが、より便利であると思われるのが、列挙型の有効な値を調査または探索できる点です。  静的関数 **Enum::GetNames** を使用すると、それぞれがテキスト形式の列挙値を含む文字列の配列が返されます。次のサンプルは、**Options** \(CLR\) 列挙型の値の列挙値を表す文字列の配列を取得し、ループ処理で結果を表示します。  
  
 **Options** 列挙型に 4 つ目のオプションを追加する場合は、この列挙型が別のアセンブリに定義されている場合でも、再コンパイルせずにこのコードから新しいオプションが報告されます。  
  
```  
// vcpp_reflection_3.cpp  
// compile with: /clr  
using namespace System;  
  
enum class Options {   // not a native enum  
   Option1, Option2, Option3  
};  
  
int main() {  
   array<String^>^ names = Enum::GetNames(Options::typeid);  
  
   Console::WriteLine("there are {0} options in enum '{1}'",   
               names->Length, Options::typeid);  
  
   for (int i = 0 ; i < names->Length ; i++)  
      Console::WriteLine("{0}: {1}", i, names[i]);  
  
   Options o = Options::Option2;  
   Console::WriteLine("value of 'o' is {0}", o);  
}  
```  
  
  **there are 3 options in enum 'Options'**  
**0: Option1**  
**1: Option2**  
**2: Option3**  
**value of 'o' is Option2**   
## 使用例  
 `GetType` オブジェクトは、型を調べるために使用できる多くのメンバーとプロパティをサポートします。  次のコードは、この情報の一部を取得して表示します。  
  
```  
// vcpp_reflection_4.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Console::WriteLine("type information for 'String':");  
   Type ^ t = String::typeid;  
  
   String ^ assemblyName = t->Assembly->FullName;  
   Console::WriteLine("assembly name: {0}", assemblyName);  
  
   String ^ nameSpace = t->Namespace;  
   Console::WriteLine("namespace: {0}", nameSpace);  
  
   String ^ baseType = t->BaseType->FullName;  
   Console::WriteLine("base type: {0}", baseType);  
  
   bool isArray = t->IsArray;  
   Console::WriteLine("is array: {0}", isArray);  
  
   bool isClass = t->IsClass;  
   Console::WriteLine("is class: {0}", isClass);  
}  
```  
  
  **type information for 'String':**  
**assembly name: mscorlib, Version\=1.0.5000.0, Culture\=neutral,**  
**PublicKeyToken\=b77a5c561934e089**  
**namespace: System**  
**base type: System.Object**  
**is array: False**  
**is class: True**   
## 使用例  
 リフレクションを使用すると、アセンブリ内の型とクラス内のメンバーも列挙できます。  この機能の例を示すために、次のような単純なクラスを定義します。  
  
```  
// vcpp_reflection_5.cpp  
// compile with: /clr /LD  
using namespace System;  
public ref class TestClass {  
   int m_i;  
public:  
   TestClass() {}  
   void SimpleTestMember1() {}  
   String ^ SimpleMember2(String ^ s) { return s; }   
   int TestMember(int i) { return i; }  
   property int Member {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
};  
```  
  
## 使用例  
 このコードを vcpp\_reflection\_6.dll という DLL にコンパイルすると、リフレクションを使用してアセンブリの内容を確認できます。  この処理を行うには、静的リフレクション API 関数 [Assembly::Load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx) を使用してアセンブリを読み込みます。  この関数が **Assembly** オブジェクトのアドレスを返すことによって、そのオブジェクト内のモジュールや型の問い合わせができるようになります。  
  
 一度、リフレクション システムがアセンブリを正常に読み込むと、[Assembly::GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx) 関数が **Type** オブジェクトの配列を取得します。  各配列要素には、異なる型の情報が含まれています。ただし、この例で定義されているクラスは 1 つだけです。  ループを使用して、この配列内の各 **Type** に対して **Type::GetMembers** 関数で型のメンバーを問い合わせます。  この関数は、**MethodInfo** オブジェクトの配列を返します。各配列要素には、メンバー関数、データ メンバー、または型のプロパティに関する情報が含まれています。  
  
 メソッドのリストには、**TestClass** で明示的に定義された関数と、**System::Object** クラスから暗黙的に継承された関数が含まれていることに注意してください。  Visual C\+\+ 構文ではなく .NET で記述されている部分では、プロパティは get 関数と set 関数でアクセスする基底のデータ メンバーとして表示されます。  get 関数と set 関数は、通常のメソッドとしてこのリストに表示されています。  リフレクションは、Visual C\+\+ コンパイラではなく、共通言語ランタイムを通じてサポートされています。  
  
 このコードを使用すると、定義したアセンブリを調べるだけでなく、.NET アセンブリを調べることもできます。  たとえば、TestAssembly を mscorlib に置き換えると、mscorlib.dll に定義されているすべての型とメソッドのリストが表示されます。  
  
```  
// vcpp_reflection_6.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
using namespace System::Reflection;  
int main() {  
   Assembly ^ a = nullptr;  
   try {  
      // load assembly -- do not use file extension  
      // will look for .dll extension first  
      // then .exe with the filename  
      a = Assembly::Load("vcpp_reflection_5");  
   }  
   catch (FileNotFoundException ^ e) {  
      Console::WriteLine(e->Message);  
      return -1;  
   }  
  
   Console::WriteLine("assembly info:");  
   Console::WriteLine(a->FullName);  
   array<Type^>^ typeArray = a->GetTypes();  
  
   Console::WriteLine("type info ({0} types):", typeArray->Length);  
  
   int totalTypes = 0;  
   int totalMembers = 0;  
   for (int i = 0 ; i < typeArray->Length ; i++) {  
      // retrieve array of member descriptions  
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();  
  
      Console::WriteLine("  members of {0} ({1} members):",   
      typeArray[i]->FullName, member->Length);  
      for (int j = 0 ; j < member->Length ; j++) {  
         Console::Write("       ({0})",   
         member[j]->MemberType.ToString() );  
         Console::Write("{0}  ", member[j]);  
         Console::WriteLine("");  
         totalMembers++;  
      }  
      totalTypes++;  
   }  
   Console::WriteLine("{0} total types, {1} total members",  
   totalTypes, totalMembers);  
}  
```  
  
## 参照  
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)