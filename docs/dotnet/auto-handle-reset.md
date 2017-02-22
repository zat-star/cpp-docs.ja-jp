---
title: "auto_handle::reset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_handle.reset"
  - "msclr::auto_handle::reset"
  - "auto_handle::reset"
  - "msclr.auto_handle.reset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::reset"
ms.assetid: 32dc3a83-80fd-45c9-8f79-8c4096c30f57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# auto_handle::reset
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在のスレッドによって所有されるオブジェクトを破棄し、必要に応じて新しいオブジェクトを所有します。  
  
## 構文  
  
```  
void reset(  
   _element_type ^ _new_ptr  
);  
void reset();  
```  
  
#### パラメーター  
 `_new_ptr`  
 \(省略可能\) 新しいオブジェクト。  
  
## 使用例  
  
```  
// msl_auto_handle_reset.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "ClassA destructor: " + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
int main()  
{  
   auto_handle<ClassA> agc1 = gcnew ClassA( "first" );  
   agc1->PrintHello();  
  
   ClassA^ ha = gcnew ClassA( "second" );  
   agc1.reset( ha ); // release first object, reference second  
   agc1->PrintHello();  
  
   agc1.reset(); // release second object, set to nullptr  
  
   Console::WriteLine( "done" );  
}  
```  
  
  **ClassA のコンストラクター: 最初**  
**Hello 最初に A ~\!**  
**ClassA のコンストラクター: 第 2**  
**ClassA のデストラクター: 最初**  
**2 番目の A から Hello\!**  
**ClassA のデストラクター: 第 2**  
**done**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\auto\_handle.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [auto\_handle Members](../dotnet/auto-handle-members.md)   
 [auto\_handle::release](../Topic/auto_handle::release.md)