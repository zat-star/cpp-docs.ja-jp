---
title: "Generics and Templates (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "generics [C++], vs. templates"
  - "templates, C++"
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generics and Templates (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ジェネリックとテンプレートは、パラメーター化された型のサポートを提供する両方の言語機能です。  ただし、異なるため、さまざまな用途に使用できます。  このトピックでは、多くの違いの概要を示します。  
  
 詳細については、「[Windows Runtime and Managed Templates](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)」および「[テンプレートの概要](../Topic/Templates%20Overview.md)」を参照してください。  
  
## テンプレートおよびジェネリックの比較  
 ジェネリックと C\+\+ テンプレートの主な違い:  
  
-   ジェネリック型がランタイムでそれらの代わりになるまで一般的です。  テンプレートはコンパイル時に特化するため、実行時にパラメーター化された型ではありません。  
  
-   共通言語ランタイムは、MSIL のジェネリックをサポートします。  ランタイムがジェネリックを認識するため、特定の型はジェネリック型を含むアセンブリを参照するときにジェネリック型に置き換えることができます。  テンプレートは、対照的に、コンパイル時に通常の型に解決され、結果の型が別のアセンブリに特化していない可能性があります。  
  
-   同じ型の引数を持つ 2 個のアセンブリに特化したジェネリックは同じ型です。  同じ型の引数を持つ 2 個のアセンブリに特化したテンプレートは、ランタイムでは、異なる型と見なされます。  
  
-   ジェネリックは、すべての参照型の引数に使用された実行可能コードに対して部分として生成されます。これは、値型ごとに一意の実装を持つ値型についても同じことはありません。  JIT コンパイラは、型引数として使用されるジェネリックについて確認し、参照型または値型のコードを最適化できます。  テンプレートは、各クラスの別のランタイム コードを生成します。  
  
-   ジェネリックは `template <int i> C {}`などの非型テンプレート パラメーターを使用しません。  テンプレートはこれらを有効にします。  
  
-   ジェネリックは、明示的な特殊化 \(つまり、特定の種類のテンプレートのカスタム実装\) を使用できません。  テンプレートです。  
  
-   ジェネリックは、部分的特殊化 \(型引数のサブセットのカスタム実装\) を使用できません。  テンプレートです。  
  
-   ジェネリック型は、パラメーターをジェネリック型の基本クラスとして使用することはできません。  テンプレートです。  
  
-   テンプレートがサポートするテンプレート テンプレート パラメーター \(たとえば。  `template<template<class T> class X> class MyClass`\)、ジェネリックではありません。  
  
## テンプレートおよびジェネリックの結合  
  
-   ジェネリックの基本的な相違点をテンプレートやジェネリックを結合するアプリケーションのビルドに影響を与えます。  たとえば、ジェネリックとして他の言語にそのテンプレートを公開する汎用ラッパーを作成するテンプレート クラスがあるとします。  テンプレートはコンパイル時にその型パラメーターを持つ必要があるジェネリックは、ランタイムの型パラメーターを解決されないため、一般的に、パスがテンプレートに型パラメーターを使用することはできません。  ジェネリック内のテンプレートを入れ子にすると、ランタイムにインスタンス化することができる任意のジェネリック型のコンパイル時にテンプレートを拡大する方法がないため、使用できません。  
  
## 例  
  
### 説明  
 次の例は、テンプレートおよびジェネリックを一緒に使用する簡単な例を次に示します。  この例では、テンプレート クラスはジェネリック型にパラメーターを渡します。  反転はできません。  
  
 この表現は、ジェネリック型には、パラメーターの追加のレイヤーを追加する必要がある場合、Visual C\+\+ アセンブリに対してローカルである、またはジェネリックでサポートされないテンプレートの特定の機能を利用するには、テンプレート コード内の既存のジェネリック API でビルドするときに使用できます。  
  
### コード  
  
```  
// templates_and_generics.cpp  
// compile with: /clr  
using namespace System;  
  
generic <class ItemType>  
ref class MyGeneric {  
   ItemType m_item;  
  
public:  
   MyGeneric(ItemType item) : m_item(item) {}  
   void F() {   
      Console::WriteLine("F");   
   }  
};  
  
template <class T>  
public ref class MyRef {  
MyGeneric<T>^ ig;  
  
public:  
   MyRef(T t) {  
      ig = gcnew MyGeneric<T>(t);  
      ig->F();  
    }      
};  
  
int main() {  
   // instantiate the template  
   MyRef<int>^ mref = gcnew MyRef<int>(11);  
}  
```  
  
### 出力  
  
```  
F  
```  
  
## 参照  
 [Generics](../windows/generics-cpp-component-extensions.md)