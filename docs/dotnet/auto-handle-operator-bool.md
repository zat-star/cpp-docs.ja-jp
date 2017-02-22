---
title: "auto_handle::operator bool | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_handle.operator bool"
  - "msclr.auto_handle.operator bool"
  - "operator bool"
  - "msclr::auto_handle::operator bool"
  - "auto_handle::operator bool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::operator bool"
ms.assetid: 2e535e99-cf87-4008-b588-02c587d77453
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# auto_handle::operator bool
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

条件式に `auto_handle` を使用するための演算子。  
  
## 構文  
  
```  
operator bool();  
```  
  
## 戻り値  
 ラップされたオブジェクトが有効な場合`true` ; 別の方法で `false`。  
  
## 解説  
 整数型に変換できないため `bool` より安全であるこの演算子は `_detail_class::_safe_bool` に変換します。  
  
## 使用例  
  
```  
// msl_auto_handle_operator_bool.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1;  
   auto_handle<String> s2 = "hi";  
   if ( s1 ) Console::WriteLine( "s1 is valid" );  
   if ( !s1 ) Console::WriteLine( "s1 is invalid" );  
   if ( s2 ) Console::WriteLine( "s2 is valid" );  
   if ( !s2 ) Console::WriteLine( "s2 is invalid" );  
   s2.reset();  
   if ( s2 ) Console::WriteLine( "s2 is now valid" );  
   if ( !s2 ) Console::WriteLine( "s2 is now invalid" );  
}  
```  
  
  **s1 が無効です。**  
**s2 は有効です。**  
**s2 で無効です。**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\auto\_handle.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [auto\_handle Members](../dotnet/auto-handle-members.md)   
 [auto\_handle::operator\!](../dotnet/auto-handle-operator-logical-not.md)