---
title: "コンパイラの警告 (レベル 4) C4232 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4232"
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 'identifier' : dllimport 'dllimport' のアドレスは静的ではありません。一貫性が保証されません。  
  
 Microsoft 拡張機能 \(\/Ze\) では、**dllimport** 修飾子を使用して宣言された関数のアドレスとして、非静的な値を指定できます。  ANSI 互換オプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) では、このように指定するとエラーが発生します。  
  
 次の例では警告 C4232 が生成されます。  
  
```  
// C4232.c  
// compile with: /W4 /Ze /c  
int __declspec(dllimport) f();  
int (*pfunc)() = &f;   // C4232  
```