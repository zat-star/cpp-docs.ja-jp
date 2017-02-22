---
title: "auto_gcroot::attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_gcroot.attach"
  - "auto_gcroot::attach"
  - "msclr::auto_gcroot::attach"
  - "msclr.auto_gcroot.attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::attach"
ms.assetid: 996ede65-bcb5-41f2-bfbf-507f8a578241
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# auto_gcroot::attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクトにアタッチ `auto_gcroot`。  
  
## 構文  
  
```  
auto_gcroot<_element_type> & attach(  
   _element_type _right  
);  
auto_gcroot<_element_type> & attach(  
   auto_gcroot<_element_type> & _right  
);  
template<typename _other_type>  
auto_gcroot<_element_type> & attach(  
   auto_gcroot<_other_type> & _right  
);  
```  
  
#### パラメーター  
 `_right`  
 アタッチするオブジェクト、またはアタッチするオブジェクトを含む `auto_gcroot`。  
  
## 戻り値  
 現在の `auto_gcroot`。  
  
## 解説  
 `_right` が `auto_gcroot`の場合は、現在の `auto_gcroot`にオブジェクトを接続する前にオブジェクトの所有権を解放します。  
  
## 使用例  
  
```  
// msl_auto_gcroot_attach.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "in ClassA constructor:" + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "in ClassA destructor:" + m_s );  
   }  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class ClassB : ClassA {  
public:  
   ClassB( String ^ s) : ClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main() {  
   auto_gcroot<ClassA^> a( gcnew ClassA( "first" ) );  
   a->PrintHello();  
   a.attach( gcnew ClassA( "second" ) ); // attach same type  
   a->PrintHello();  
   ClassA^ ha = gcnew ClassA( "third" );  
   a.attach( ha ); // attach raw handle  
   a->PrintHello();  
   auto_gcroot<ClassB^> b( gcnew ClassB("fourth") );  
   b->PrintHello();  
   a.attach( b ); // attach derived type  
   a->PrintHello();  
}  
```  
  
  **ClassA のコンストラクター: 最初**  
**Hello 最初に A ~\!**  
**ClassA のコンストラクター: 第 2**  
**ClassA のデストラクター: 最初**  
**2 番目の A から Hello\!**  
**ClassA のコンストラクター: 3 番目の**  
**ClassA のデストラクター: 第 2**  
**3 番目の A から Hello\!**  
**ClassA のコンストラクター: 4 番目の**  
**4 番目の B から Hello\!**  
**ClassA のデストラクター: 3 番目の**  
**4 番目の A から Hello\!**  
**ClassA のデストラクター: 4 番目の**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\auto\_gcroot.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [auto\_gcroot Members](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::operator\=](../dotnet/auto-gcroot-operator-assign.md)   
 [auto\_gcroot::release](../dotnet/auto-gcroot-release.md)