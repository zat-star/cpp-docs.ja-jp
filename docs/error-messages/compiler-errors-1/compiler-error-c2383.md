---
title: "コンパイラ エラー C2383 | Microsoft Docs"
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
  - "C2383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2383"
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol'' : 既定の引数をこのシンボルで使用できません。  
  
 C\+\+ コンパイラでは、関数へのポインターに既定の引数は使用できません。  
  
 このコードは、以前のバージョンのコンパイラでは許容されましたが、現在はエラーになります。  すべてのバージョンの Visual C\+\+ で動作するコードを作成するには、関数へのポインターの引数に既定の値を代入しないでください。  
  
 次の行では C2383 エラーが生成されます。  
  
```  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```