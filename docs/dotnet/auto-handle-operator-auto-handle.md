---
title: "auto_handle::operator auto_handle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr.auto_handle.operator auto_handle"
  - "operator auto_handle"
  - "msclr::auto_handle::operator auto_handle"
  - "auto_handle.operator auto_handle"
  - "auto_handle::operator auto_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "演算子 auto_handle"
ms.assetid: 2f8b35d1-2783-4d91-b6fb-eae551270fb8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# auto_handle::operator auto_handle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`auto_handle` と互換性のある型間の演算子を型に選択します。  
  
## 構文  
  
```  
template<typename _other_type>  
operator auto_handle<_other_type>();  
```  
  
## 戻り値  
 `auto_handle<_other_type>`にキャストされる現在の `auto_handle`。  
  
## 使用例  
  
```  
// msl_auto_handle_op_auto_handle.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {}  
  
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
   auto_handle<ClassB> b = gcnew ClassB("first");  
   b->PrintHello();  
   auto_handle<ClassA> a = (auto_handle<ClassA>)b;  
   a->PrintHello();  
}  
```  
  
  **Hello 最初 B から\!**  
**Hello 最初に A ~\!**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\auto\_handle.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [auto\_handle Members](../dotnet/auto-handle-members.md)