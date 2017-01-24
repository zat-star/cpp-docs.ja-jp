---
title: "コンパイラ エラー C3248 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3248"
ms.assetid: d00b9d7d-b6be-4a5b-bb52-48174ea71fc4
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function1': '\_\_sealed' として宣言されている関数は、'function2' によってオーバーライドすることはできません  
  
 派生クラスが [\_\_sealed](../../misc/sealed.md) 仮想メソッドをオーバーライドしようとしました。  
  
 C3248 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
 次の例では C3248 が生成されます。  
  
```  
// C3248b.cpp // compile with: /clr:oldSyntax using namespace System; __gc struct B { __sealed virtual void func(); }; __gc struct D : B { void func();   // C3248 };  
```