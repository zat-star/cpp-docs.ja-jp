---
title: "コンパイラ エラー C3915 | Microsoft Docs"
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
  - "C3915"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3915"
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3915
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' には、既定のインデックス付きのプロパティ \(クラス インデクサー\) がありません  
  
 型に既定のインデックス付きプロパティがありません。  
  
 詳細については、「[プロパティ](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3915 エラーが生成されます。  
  
```  
// C3915.cpp  
// compile with: /clr  
ref class X {  
public:  
// uncomment property to resolve this C3915  
//   property int default[]  
//   {  
//      int get(int i)  
//      {  
//         return 863;  
//      }  
//   }  
};  
  
int main() {  
   X^ x = new X;  
   System::Console::WriteLine(x[1]);   // C3915  
}  
```  
  
## 使用例  
 <xref:System.Reflection.DefaultMemberAttribute> を指定して既定のインデクサーを定義したコンパイル単位で既定のインデクサーを使おうとした場合も、C3915 エラーが発生します。  
  
 次の例では C3915 エラーが生成されます。  
  
```  
// C3915_b.cpp  
// compile with: /clr  
using namespace System;  
  
[Reflection::DefaultMember("XXX")]  
ref struct A {  
   property Double XXX[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
  
ref struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
   Console::WriteLine("{0}", mya[3]);   // C3915  
  
   B ^ myb = gcnew B();  
   Console::WriteLine("{0}", myb[3]);   // OK  
}  
```