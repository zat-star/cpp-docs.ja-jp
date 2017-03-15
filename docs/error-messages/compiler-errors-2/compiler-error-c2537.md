---
title: "コンパイラ エラー C2537 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2537"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2537"
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2537
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specifier' : リンケージ指定子は使用できません。  
  
 以下の原因が考えられます。  
  
1.  リンケージ指定子がサポートされていません。  サポートされているのは "C" のリンケージ指定子だけです。  
  
2.  "C" リンケージが、オーバーロードされた一連の関数内の複数の関数に対して指定されています。  これは認められていません。  
  
 次の例では警告 C2537 が生成されます。  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```