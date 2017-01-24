---
title: "コンパイラ エラー C2691 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2691"
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'データ型' : マネージ配列または WinRT 配列にはこの要素型を指定できません  
  
 マネージ配列または WinRT 配列の要素の型は、値型または参照型になります。  
  
 次の例では C2691 が生成されます。  
  
```  
// C2691a.cpp  
// compile with: /clr  
class A {};  
  
int main() {  
   array<A>^ a1 = gcnew array<A>(20);   // C2691  
   array<int>^ a2 = gcnew array<int>(20);   // value type OK  
}  
```  
  
 次の例では C2691 が生成されます。  
  
```  
// C2691b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
int main() {  
   int * a1 __gc[];   // C2691  
   int * a1 = new int [20];   // OK  
}  
```  
  
 C2691 は、C\+\+ マネージ拡張を使用してジャグ配列を定義しようとした場合にも発生します。  ジャグ配列は現在の構文でサポートされています。詳細については、「[Arrays](../../windows/arrays-cpp-component-extensions.md)」を参照してください。  
  
 次の例では C2691 が生成されます。  
  
```  
// C2691c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
int main() {  
   Int32 myJaggedArray[][] = new Int32 [50][];   // C2691  
}  
```