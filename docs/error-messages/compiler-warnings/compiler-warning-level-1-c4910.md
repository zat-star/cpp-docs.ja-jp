---
title: "コンパイラの警告 (レベル 1) C4910 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4910"
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\<identifier\>' : 明示的なインスタンス化では '\_\_declspec\(dllexport\)' と 'extern' は互換性がありません  
  
 明示的なテンプレートのインスタンス化 *\<identifier\>* が、`__declspec(dllexport)` と `extern` の両方のキーワードによって変更されました。 ただし、これらのキーワードは、相互に排他的です。`__declspec(dllexport)` キーワードは、テンプレート クラスのインスタンス化を意味しますが、`extern` キーワードは、テンプレート クラスを自動的にインスタンス化しないことを意味します。  
  
## 参照  
 [明示的なインスタンス化](../Topic/Explicit%20Instantiation.md)   
 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)   
 [一般的な規則と制約](../../cpp/general-rules-and-limitations.md)