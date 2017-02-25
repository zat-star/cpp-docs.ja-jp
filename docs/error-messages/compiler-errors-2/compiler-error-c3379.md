---
title: "コンパイラ エラー C3379 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3379"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3379"
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3379
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 入れ子になったクラスに宣言の一部としてアセンブリ アクセス指定子を含めることはできません。  
  
 クラスや構造体などのマネージ型に適用されている [public](../../cpp/public-cpp.md) キーワードと [private](../Topic/private%20\(C++\).md) キーワードは、クラスがアセンブリ メタデータを通じて公開されるかどうかを示します。  入れ子になったクラスには `public` または `private` を適用できず、外側のクラスのアセンブリ アクセスを継承します。  
  
 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) と共に使用した場合、`ref` キーワードおよび `value` キーワードはクラスがマネージ クラスであることを示します \(「[Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください\)。  
  
 次の例では警告 C3379 が生成されます。  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  
  
 次の例では警告 C3379 が生成されます。  
  
```  
// C3379b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
public __gc class A {  
public:  
   static int i = 9;  
  
   public __gc class BA {   // C3379  
   // try the following line instead  
   // __gc class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A *myA = new A;  
   Console::WriteLine(myA->i);  
  
   A::BA *myBA = new A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```