---
title: "コンパイラ エラー C3369 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3369"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3369"
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3369
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'module name': 既に定義された idl\_module  
  
 DLL の定義に [idl\_module](../../windows/idl-module.md) を使用できるのは、プログラム内で 1 回だけです。  
  
 次の例では C3369 が生成されます。  
  
```  
// C3369.cpp // compile with: /c [idl_module(name="name1", dllname="x.dll")]; // C3369 [idl_module(name="name1", dllname="x.dll")];  
```