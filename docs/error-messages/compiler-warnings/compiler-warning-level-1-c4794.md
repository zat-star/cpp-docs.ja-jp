---
title: "コンパイラの警告 (レベル 1) C4794 | Microsoft Docs"
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
  - "C4794"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4794"
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4794
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スレッドのローカル ストレージ変数 'variable' のセグメントが 'section name' から '.tls$' に変更されました  
  
 tls 変数を .tls$ で始まっていないセクションに配置するために [\#pragma data\_seg](../../preprocessor/data-seg.md) を使用しました。  
  
 .tls$*x* セクションは、[\_\_declspec\(thread\)](../../cpp/thread.md) 変数が定義されているオブジェクト ファイルに存在します。 EXE または DLL の .tls セクションはこれらのセクションから生成されます。  
  
## 使用例  
 次の例では C4794 が生成されます。  
  
```  
// C4794.cpp // compile with: /W1 /c #pragma data_seg(".someseg") __declspec(thread) int i;   // C4794 // OK #pragma data_seg(".tls$9") __declspec(thread) int j;  
```