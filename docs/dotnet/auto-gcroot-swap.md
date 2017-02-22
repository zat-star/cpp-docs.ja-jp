---
title: "auto_gcroot::swap | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr.auto_gcroot.swap"
  - "msclr::auto_gcroot::swap"
  - "auto_gcroot::swap"
  - "auto_gcroot.swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::swap"
ms.assetid: 4915c629-6a53-432c-8155-3a7511dc70cb
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# auto_gcroot::swap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

別の `auto_gcroot`の交換オブジェクト。  
  
## 構文  
  
```  
void swap(  
   auto_gcroot<_element_type> & _right  
);  
```  
  
#### パラメーター  
 `_right`  
 オブジェクトを交換する `auto_gcroot`。  
  
## 使用例  
  
```  
// msl_auto_gcroot_swap.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_gcroot<String^> s1 = "string one";  
   auto_gcroot<String^> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   s1.swap( s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
  **s1 \= 「String 1 " s2 \= 「String 2」**  
**s1 \= 「String 2 " s2 \= 「String 1」**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\auto\_gcroot.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [auto\_gcroot Members](../dotnet/auto-gcroot-members.md)   
 [swap 関数 \(auto\_gcroot\)](../dotnet/swap-function-auto-gcroot.md)