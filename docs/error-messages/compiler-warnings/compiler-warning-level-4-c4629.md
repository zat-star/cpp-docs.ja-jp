---
title: "コンパイラの警告 (レベル 4) C4629 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4629"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4629"
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4629
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

digraph が使用されました。文字のシーケンス 'digraph' はトークン 'char' として解釈されます。\(これが意図でない場合は、2 文字の間にスペースを挿入してください\)  
  
 コンパイラで [\/Za](../../build/reference/za-ze-disable-language-extensions.md) を使用すると、digraph の検出時に警告が表示されます。  
  
 次の例では C4629 が生成されます。  
  
```  
// C4629.cpp // compile with: /Za /W4 int main() <%   // C4629 <% digraph for { }  
```