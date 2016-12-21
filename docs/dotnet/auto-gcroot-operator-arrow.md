---
title: "auto_gcroot::operator-&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_gcroot.operator->"
  - "msclr::auto_gcroot::operator->"
  - "auto_gcroot::operator->"
  - "msclr.auto_gcroot.operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator->"
ms.assetid: 2c77bc53-5f77-4544-9485-c950cd8e0bb1
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::operator-&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メンバー アクセス演算子。  
  
## 構文  
  
```  
_element_type operator->() const;  
```  
  
## 戻り値  
 `auto_gcroot` によりラップされるオブジェクト。  
  
## 使用例  
  
```  
// msl_auto_gcroot_op_arrow.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
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
  
   int m_i;  
};  
  
int main() {  
   auto_gcroot<ClassA^> a( gcnew ClassA( "first" ) );  
   a->PrintHello();  
  
   a->m_i = 5;  
   Console::WriteLine( "a->m_i = {0}", a->m_i );  
}  
```  
  
  **Hello 最初に A ~\!**  
**次の\>\_i \= 5**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\auto\_gcroot.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [auto\_gcroot Members](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::get](../dotnet/auto-gcroot-get.md)