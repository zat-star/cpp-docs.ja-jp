---
title: "コンパイラ エラー C3641 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3641"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3641"
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3641
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : \/clr:pure または \/clr:safe と共にコンパイルされた関数に対する呼び出し規約 'calling\_convention' が無効です  
  
 [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md) で使用できるのは、[\_\_clrcall](../../cpp/clrcall.md) 呼び出し規約だけです。  
  
 次の例では警告 C3641 が生成されます。  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```