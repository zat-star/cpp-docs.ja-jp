---
title: "コンパイラ エラー C2142 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2142"
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数の宣言に可変個引数リストが含まれているものといないものが存在します。  
  
 この関数の宣言の 1 つには可変個パラメーター リストが含まれています。  別の宣言には含まれていません。  ANSI C \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) オプションを指定したときだけに発生します。  
  
 次の例では警告 C2142 が生成されます。  
  
```  
// C2142.c  
// compile with: /Za /c  
void func();  
void func( int, ... );   // C2142  
void func2( int, ... );   // OK  
```