---
title: "コンパイラの警告 (レベル 1) C4237 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4237"
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'キーワード' キーワードはサポートされていませんが、将来の拡張のために予約されています  
  
 C\+\+ 仕様のキーワードは Visual C\+\+ コンパイラには実装されていませんが、これらのキーワードをユーザー定義のシンボルとして使用することはできません。  
  
 次の例では警告 C4237 が生成されます。  
  
```  
// C4237.cpp  
// compile with: /W1 /c  
int export;   // C4237  
```