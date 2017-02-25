---
title: "コンパイラの警告 (レベル 4) C4062 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4062"
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 4) C4062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

列挙型 'enumeration' を切り替えた列挙子 'identifier' はハンドルされません  
  
 列挙子には、`switch` ステートメントに関連付けられたハンドラーがなく、**既定**のラベルがありません。  
  
 既定では、この警告はオフに設定されています。 詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 次の例では C4062 が生成されます。  
  
```  
// C4062.cpp // compile with: /W4 #pragma warning(default : 4062) enum E { a, b, c }; void func ( E e ) { switch(e) { case a: case b: break;   // no default label }   // C4062, enumerate 'c' not handled } int main() { }  
```