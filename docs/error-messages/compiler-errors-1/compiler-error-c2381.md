---
title: "コンパイラ エラー C2381 | Microsoft Docs"
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
  - "C2381"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2381"
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2381
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 再定義 ; \_\_declspec\(noreturn\) が異なります。  
  
 関数が宣言されてから定義されていますが、定義で [noreturn](../../cpp/noreturn.md) `__declspec` 修飾子が使用されています。  `noreturn` を使用すると、関数の再定義が指定されます。宣言と定義は `noreturn` の使用と対応している必要があります。  
  
 次の例では警告 C2381 が生成されます。  
  
```  
// C2381.cpp  
// compile with: /c  
void f1();  
void __declspec(noreturn) f1() {}   // C2381  
void __declspec(noreturn) f2() {}   // OK  
```