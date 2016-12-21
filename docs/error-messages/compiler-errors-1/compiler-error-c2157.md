---
title: "コンパイラ エラー C2157 | Microsoft Docs"
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
  - "C2157"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2157"
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2157
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : プラグマ リスト内で参照される前に宣言されていなければなりません  
  
 [alloc\_text](../../preprocessor/alloc-text.md) プラグマの関数の一覧で参照される前に関数名が宣言されていません。  
  
 次の例では C2157 が生成されます。  
  
```  
// C2157.cpp // compile with: /c #pragma alloc_text( "func", func)   // C2157 // OK extern "C" void func(); #pragma alloc_text( "func", func)  
```