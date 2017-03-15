---
title: "コンパイラ エラー C3519 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3519"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3519"
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3519
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'invalid\_param' : embedded\_idl 属性への無効なパラメーターです  
  
 パラメーターが [\#import](../Topic/%23import%20Directive%20\(C++\).md) の `embedded_idl` 属性に渡されましたが、コンパイラはそのパラメーターを認識しませんでした。  
  
 `embedded_idl` で指定できるパラメーターは、`emitidl` および `no_emitidl` だけです。  
  
 次の例では警告 C3519 が生成されます。  
  
```  
// C3519.cpp  
// compile with: /LD  
[module(name="MyLib2")];  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")     
// C3519  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")     
// OK  
```