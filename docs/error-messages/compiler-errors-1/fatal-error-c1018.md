---
title: "致命的なエラー C1018 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1018"
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 致命的なエラー C1018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

予期しない \#elif です。  
  
 `#elif` ディレクティブが、`#if`、`#ifdef`、または `#ifndef` コンストラクトの外側に置かれています。`#elif` は、これらのコンストラクトのいずれかの内側だけで使用してください。  
  
 次の例では C1018 が生成されます。  
  
```  
// C1018.cpp #elif      // C1018 #endif int main() {}  
```  
  
 考えられる解決策:  
  
```  
// C1018b.cpp #if 1 #elif #endif int main() {}  
```