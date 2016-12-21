---
title: "コンパイラの警告 (レベル 4) C4130 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4130"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4130"
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4130
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': 文字列定数のアドレスで論理演算が行われました  
  
 文字列リテラルのアドレスで演算子が使用されると、不要なコードが生成されます。  
  
 次の例では C4130 が生成されます。  
  
```  
// C4130.cpp // compile with: /W4 int main() { char *pc; pc = "Hello"; if (pc == "Hello") // C4130 { } }  
```  
  
 **if** ステートメントは、ポインター `pc` に格納されている値と、コード内に出現するたびに個別に割り当てられる文字列 "Hello" のアドレスを比較しています。**if** ステートメントは、`pc` が指す文字列と、文字列 "Hello" については比較しません。  
  
 文字列を比較するには、`strcmp` 関数を使用します。