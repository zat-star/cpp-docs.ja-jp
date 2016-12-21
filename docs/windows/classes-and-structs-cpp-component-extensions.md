---
title: "Classes and Structs  (C++ Component Extensions) | Microsoft Docs"
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
  - "public"
  - "ref struct"
  - "value_CPP"
  - "ref class"
  - "value struct"
  - "ref struct_cpp"
  - "ref class_cpp"
  - "value class_cpp"
  - "value struct_cpp"
  - "value class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ref class keyword [C++]"
  - "value class keyword [C++]"
  - "value struct keyword [C++]"
  - "ref struct keyword [C++]"
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes and Structs  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*オブジェクトの有効期間*が自動的に管理されるクラスまたは構造体を宣言します。  Visual C\+\+ では、オブジェクトがアクセス不能になるかスコープ外になると、そのオブジェクトに割り当てられているメモリを自動的に破棄します。  
  
## すべてのランタイム  
 **構文**  
  
```  
  
          class_access ref class    name modifier :  inherit_access base_type {};  
class_access ref struct   name modifier :  inherit_access base_type {};  
class_access value class  name modifier :  inherit_access base_type {};  
class_access value struct name modifier :  inherit_access base_type {};  
  
```  
  
 **パラメーター**  
  
 *class\_access* \(省略可能\)  
 アセンブリの外部にあるクラスまたは構造体のアクセシビリティ。  使用可能な値は **public** と `private` です \(既定値は `private`\)。  入れ子になったクラスまたは構造体には *class\_access* 指定子を指定できません。  
  
 *name*  
 クラスまたは構造体の名前。  
  
 *modifier* \(省略可能\)  
 有効な修飾子は、[abstract](../windows/abstract-cpp-component-extensions.md) と [sealed](../windows/sealed-cpp-component-extensions.md) です。  
  
 *inherit\_access* \(省略可能\)  
 `base_type` のアクセシビリティ。  許可されているアクセシビリティは `public` のみです \(既定値は `public`\)。  
  
 *base\_type* \(省略可能\)  
 基本型。  ただし、値型を基本型として使用することはできません。  
  
 詳細については、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]と[!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]に関するセクションで、このパラメーターの言語別の説明を参照してください。  
  
 **コメント**  
  
 **ref class** または **value class** で宣言されたオブジェクトの既定のメンバー アクセシビリティは `private` です。  また、**ref struct** または **value struct** で宣言されたオブジェクトの既定のメンバー アクセシビリティは `public` です。  
  
 参照型が別の参照型から継承される場合、基本クラスの仮想関数は明示的にオーバーライドするか \([override](../windows/override-cpp-component-extensions.md) を使用\)、非表示にする \([new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md) を使用\) 必要があります。  派生クラスの関数は、明示的に `virtual` と指定する必要があります。  
  
 コンパイル時に型が `ref class` と `ref struct` のどちらであるか、または `value class` と `value struct` のどちらであるかを検出するには、`__is_ref_class (``type``)`、`__is_value_class (``type``)`、 `__is_simple_value_class (``type``)` のいずれかを使用します。  詳細については、「[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)」を参照してください。  
  
 クラスと構造体の詳細については、以下のページを参照してください。  
  
-   [クラスと構造体のインスタンス化](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
-   [値型および参照型における this ポインターのセマンティクス](../misc/semantics-of-the-this-pointer-in-value-and-reference-types.md)  
  
-   [参照型の C\+\+ スタック セマンティクス](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [クラス、構造体、および共用体](../Topic/Classes%20and%20Structs%20\(C++\).md)  
  
-   [ネイティブ クラスでの public と private](../misc/how-to-declare-public-and-private-on-native-classes.md)  
  
-   [暗黙的抽象クラス](../misc/implicitly-abstract-classes.md)  
  
-   [クラスまたは構造体の静的コンストラクターを定義する](../misc/how-to-define-static-constructors-in-a-class-or-struct.md)  
  
-   [コピー コンストラクターを生成することができません](../Topic/Copy%20Constructor%20May%20Not%20Be%20Generated.md)  
  
-   [参照型のシグネチャによる隠ぺいの関数](../misc/hide-by-signature-functions-in-reference-types.md)  
  
-   [Visual C\+\+ のデストラクターおよびファイナライザー](../misc/destructors-and-finalizers-in-visual-cpp.md)  
  
-   [型およびメンバーの可視性](../Topic/Type%20and%20Member%20Visibility.md)  
  
-   [ユーザー定義の演算子](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [ユーザー定義変換](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [方法: ネイティブ クラスを C\# で使用できるようにラップする](../Topic/How%20to:%20Wrap%20Native%20Class%20for%20Use%20by%20C%23.md)  
  
-   [Generic Classes \(C\+\+\/CLI\)](../Topic/Generic%20Classes%20\(C++-CLI\).md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **コメント**  
  
 詳細については、「[Ref クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)」および「[値クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx)」を参照してください。  
  
 **パラメーター**  
  
 *base\_type* \(省略可能\)  
 基本型。  `ref class` または `ref struct` は、0 個以上のインターフェイスおよび 0 個または 1 個の `ref` 型から継承できます。  `value class` または `value struct` は、0 個以上のインターフェイスからのみ継承できます。  
  
 `ref class` キーワードまたは `ref struct` キーワードを使用してオブジェクトを宣言する場合、オブジェクトに対するハンドル \(オブジェクトへの参照カウンター ポインター\) を使用してオブジェクトにアクセスします。  宣言された変数がスコープ外になると、コンパイラは自動的に基になるオブジェクトを削除します。  そのオブジェクトが呼び出しのパラメーターとして使用されているか、変数に格納されている場合は、実際にそのオブジェクトのハンドルが渡されるか格納されます。  
  
 `value class` キーワードまたは `value struct` キーワードを使用してオブジェクトを宣言すると、宣言されたオブジェクトのオブジェクト有効期間は監視されません。  このオブジェクトは、C\+\+ の他の標準のクラスや構造体と同様です。  
  
### 必要条件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **コメント**  
  
 次の表に、「**すべてのランタイム**」セクションに示されている構文の C\+\+\/CLI に固有の違いを示します。  
  
 **パラメーター**  
  
 *base\_type* \(省略可能\)  
 基本型。  `ref class` または `ref struct` は、0 個以上のマネージ インターフェイスおよび 0 個または 1 個の ref 型から継承できます。  `value class` または `value struct` は、0 個以上のマネージ インターフェイスからのみ継承できます。  
  
 `ref class` と `ref struct` キーワードを指定すると、コンパイラはクラスまたは構造体をヒープに割り当てます。  そのオブジェクトが呼び出しのパラメーターとして使用されているか、変数に格納されている場合は、実際にそのオブジェクトへの参照が渡されるか格納されます。  
  
 `value class` キーワードと `value struct` キーワードを指定すると、割り当てられたクラスまたは構造体の値が関数に渡されるか、メンバーに格納されます。  
  
### 必要条件  
 コンパイラ オプション: **\/clr**  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)