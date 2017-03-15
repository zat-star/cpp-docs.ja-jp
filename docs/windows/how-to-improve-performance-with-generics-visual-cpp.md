---
title: "How to: Improve Performance with Generics (Visual C++) | Microsoft Docs"
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
  - "performance, C++"
  - "Visual C++, performance"
  - "Visual C++, generics"
  - "generics [C++], performance"
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
caps.latest.revision: 7
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Improve Performance with Generics (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ジェネリックを使用すると、型パラメーターに基づいて再利用可能なコードを作成できます。  型パラメーターの実際の型はクライアント コードによって呼び出されるまで延期されます。  ジェネリックの詳細については、「[Generics](../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
 この記事では、ジェネリック コレクションを使用するアプリケーションのパフォーマンスを向上する方法について説明します。  
  
## 使用例  
 .NET Framework は <xref:System.Collections?displayProperty=fullName> の名前空間のコレクション クラスが用意されています。  これらのコレクションのほとんどは <xref:System.Object?displayProperty=fullName>型のオブジェクトを操作します。  これは <xref:System.Object?displayProperty=fullName>からすべてが .NET Framework に入力するため、コレクションが、値型、派生します型を格納できます。  ただし、この方法には 2 種類の短所があります。  
  
 最初にコレクションが整数などの値型を格納する場合、値はコレクションに追加し、前に値をコレクションから取得されるときにボックス化解除にボックス化する必要があります。  これらは、操作です。  
  
 第 2 に、制御するコレクションに追加できる入力する方法はありません。  ユーザーが同じ場合は、意図したものではありませんが、完全に、コレクションに整数と文字列を追加する場合があります。  このコードは、にタイプ セーフで、コレクションから取得される型は実際には意図したものであることを確認する必要があります。  
  
 次のコード例、ジェネリック型の前に .NET Framework のコレクションの 2 種類の主要な欠点を示します。  
  
```  
// perf_pre_generics.cpp  
// compile with: /clr  
  
using namespace System;  
using namespace System::Collections;  
  
int main()  
{  
    // This Stack can contain any type.  
    Stack ^s = gcnew Stack();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
  
    // Push a String to the same Stack.  
    // The Stack now contains two different data types.  
    s->Push("Seven");  
  
    // Pop the items off the Stack.  
    // The item is returned as an Object, so a cast is  
    // necessary to convert it to its proper type.  
    while (s->Count > 0)  
    {  
        Object ^o = s->Pop();  
        if (o->GetType() == Type::GetType("System.String"))  
        {  
            Console::WriteLine("Popped a String: {0}", (String ^)o);  
        }  
        else if (o->GetType() == Type::GetType("System.Int32"))  
        {  
            Console::WriteLine("Popped an int: {0}", (int)o);  
        }  
        else  
        {  
            Console::WriteLine("Popped an unknown type!");  
        }  
    }  
}  
```  
  
  **文字列をポップされます。: 7**  
**int をポップされます。: 7**   
## 使用例  
 <xref:System.Collections.Generic?displayProperty=fullName> の新しい名前空間を <xref:System.Collections?displayProperty=fullName> の名前空間にある同じコレクションが数多く用意されていますが、ジェネリック型パラメーターを受け入れるように変更されました。  これは非ジェネリック コレクションの 2 種類の欠点を削除する: 値型のボックス化およびボックス化解除およびコレクションに格納される型を指定できない。  2 種類のコレクションの動作は同じです。; これらはどのようにのみインスタンス化されるかは異なります。  
  
 上に表示される <xref:System.Collections.Generic.Stack%601> の一般的なコレクションを使用してこの例と例を比較します。  頻繁にアクセスされる大規模なコレクションで、この例のパフォーマンスは、前の例よりも大きくなります。  
  
```  
// perf_post_generics.cpp  
// compile with: /clr  
  
#using <System.dll>  
  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main()  
{  
    // This Stack can only contain integers.  
    Stack<int> ^s = gcnew Stack<int>();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
    s->Push(14);  
  
    // You can no longer push a String to the same Stack.  
    // This will result in compile time error C2664.  
    //s->Push("Seven");  
  
    // Pop an item off the Stack.  
    // The item is returned as the type of the collection, so no  
    // casting is necessary and no unboxing is performed for  
    // value types.  
    int i = s->Pop();  
    Console::WriteLine(i);  
  
    // You can no longer retrieve a String from the Stack.  
    // This will result in compile time error C2440.  
    //String ^str = s->Pop();  
}  
```  
  
  **14**   
## 参照  
 [Generics](../windows/generics-cpp-component-extensions.md)