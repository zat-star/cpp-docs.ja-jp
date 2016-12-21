---
title: "致命的なエラー C1016 | Microsoft Docs"
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
  - "C1016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1016"
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#ifdef には識別子が必要です \#ifndef には識別子が必要です  
  
 条件付きコンパイル ディレクティブ \([\#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) または `#ifndef`\) に、評価する識別子が指定されていません。 このエラーを解決するには、識別子を指定してください。  
  
 次の例では C1016 が生成されます。  
  
```  
// C1016.cpp #ifdef   // C1016 #define FC1016 #endif int main() {}  
```  
  
 考えられる解決策:  
  
```  
// C1016b.cpp #ifdef X #define FC1016 #endif int main() {}  
```