---
title: "コンパイラ エラー C3225 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3225"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3225"
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラ エラー C3225
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' のジェネリック型引数を '型' にすることはできません。値型またはハンドル型にしなければなりません  
  
 ジェネリック型引数が正しい型ではありませんでした。  
  
 詳細については、「[Generics](../../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 ジェネリック型をネイティブ型でインスタンス化することはできません。  次の例では C3225 エラーが生成されます。  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## 使用例  
 C\# を使用してコンポーネントを作成する例を次に示します。  制約で、ジェネリック型は値型でのみインスタンス化できることが指定されています。  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## 使用例  
 この例では、C\# で作成したコンポーネントを使用しているので、MyList は <xref:System.Nullable> 以外の値型でのみインスタンス化できるという制約に違反します。  次の例では C3225 エラーが生成されます。  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```