---
title: "コンパイラの警告 (レベル 1) C4272 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4272"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4272"
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 1) C4272
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : \_\_declspec\(dllimport\) に設定されています。関数をインポートするときは、ネイティブ呼び出し規約を指定しなければなりません。  
  
 これは、[\_\_clrcall](../../cpp/clrcall.md) 呼び出し規約を使用してマークされた関数をエクスポートするためのエラーです。`__clrcall` としてマークされた関数をインポートしようとすると、この警告が表示されます。  
  
 次の例では警告 C4272 が生成されます。  
  
```  
// C4272.cpp  
// compile with: /c /W1 /clr  
__declspec(dllimport) void __clrcall Test();   // C4272  
__declspec(dllimport) void Test2();   // OK  
```