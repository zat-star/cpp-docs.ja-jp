---
title: "コンパイラ エラー C3185 | Microsoft Docs"
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
  - "C3185"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3185"
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3185
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マネージまたは WinRT 型 'type' で 'typeid' が使用されました。代わりに 'operator' を使用してください  
  
 [typeid](../../cpp/typeid-operator.md) 演算子をマネージまたは WinRT 型に適用することはできません。代わりに [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) を使用してください。  
  
 次の例は C3185 を生成し、その修正方法を示しています。  
  
```  
// C3185a.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
  
int main() {  
   Derived ^ pd = gcnew Derived;  
   Base ^pb = pd;  
   const type_info & t1 = typeid(pb);   // C3185  
   System::Type ^ MyType = Base::typeid;   // OK  
};  
```  
  
 **C\+\+ マネージ拡張**  
  
 マネージ型に [typeid](../../cpp/typeid-operator.md) を適用することはできません。代わりに [\_\_typeof](../../misc/typeof.md) を使用してください。  
  
 次の例では C3185 が生成されます。  
  
```  
// C3185b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class Base {};  
__gc class Derived : public Base {};  
  
int main() {  
   Derived *pd = new Derived;  
   Base *pb = pd;  
   const type_info & t1 = typeid(*pb);   // C3185  
  
   // OK  
   Type * t = __typeof(Base);  
   Type * t1 = __typeof(Derived);  
};  
```