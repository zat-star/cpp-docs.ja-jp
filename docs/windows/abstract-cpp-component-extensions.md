---
title: "abstract  (C++ Component Extensions) | Microsoft Docs"
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
  - "abstract"
  - "abstract_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abstract keyword [C++]"
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# abstract  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`abstract` キーワードは、次のいずれかを宣言します。  
  
-   型を基本データ型として使用できるが、型自体はインスタンス化できない。  
  
-   型のメンバー関数を派生型でのみ定義できる。  
  
## すべてのプラットフォーム  
 **構文**  
  
```  
  
class-declaration class-identifier abstract {}  
virtual return-type member-function-identifier() abstract ;  
  
```  
  
 **コメント**  
  
 最初の例の構文では、abstract \(抽象\) にするクラスを宣言します。  *class\-declaration* コンポーネントは、**\/ZW** または **\/clr** のコンパイラ オプションを指定した場合は、ネイティブ C\+\+ の宣言 \(`class` または `struct`\) か、C \+\+ の拡張宣言 \(`ref class` または `ref struct`\) になります。  
  
 2 つ目の例の構文では、仮想メンバー関数を抽象として宣言します。  関数を抽象として宣言することは、純粋仮想関数として宣言することと同じです。  メンバー関数を抽象として宣言すると、外側のクラスも抽象として宣言されます。  
  
 `abstract` キーワードはネイティブ コードとプラットフォーム固有のコードでサポートされます。つまり、コンパイラ オプション **\/ZW** または **\/clr** を指定してもしなくてもコンパイルできます。  
  
 コンパイル時に、型の特徴が `__is_abstract(``type``)` である抽象型かどうかを検出できます。  詳細については、「[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)」を参照してください。  
  
 `abstract` キーワードは状況依存のオーバーライド指定子です。  状況依存のキーワードの詳細については、「[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。  オーバーライド指定子の詳細については、「[方法: ネイティブ コンパイルでオーバーライド指定子を宣言する](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)」を参照してください。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 詳細については、「[Ref クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)」を参照してください。  
  
### 必要条件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
  
### 必要条件  
 コンパイラ オプション: **\/clr**  
  
### 使用例  
 **例**  
  
 次のコード例では、`X` クラスに `abstract` が指定されているため、エラーが生成されます。  
  
```  
// abstract_keyword.cpp  
// compile with: /clr  
ref class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X;   // C3622  
}  
```  
  
 **例**  
  
 次のコード例では、`abstract` として指定されたネイティブ クラスがインスタンス化されるため、エラーが生成されます。  このエラーは **\/clr** コンパイラ オプションの有無にかかわらず発生します。  
  
```  
// abstract_keyword_2.cpp  
class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'  
                    // cannot be instantiated. See declaration of 'X'}  
  
```  
  
 **例**  
  
 次のコード例では、関数 `f` に定義が含まれている一方で `abstract` が指定されているため、エラーが生成されます。  この例の最後のステートメントで、抽象仮想関数を宣言することは純粋仮想関数を宣言することと同じであることを示しています。  
  
```  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)