---
title: "コンパイラ エラー C2197 | Microsoft Docs"
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
  - "C2197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2197"
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 呼び出しに対する引数が多すぎます  
  
 コンパイラで検出された関数を呼び出すためのパラメーターが多すぎるか、または関数の宣言が正しくありません。  
  
 次の例では C2197 が生成されます。  
  
```  
// C2197.c // compile with: /Za /c void func( int ); int main() { func( 1, 2 );   // C2197 two actual parameters func( 2 );   // OK }  
```