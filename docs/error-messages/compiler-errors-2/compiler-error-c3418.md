---
title: "コンパイラ エラー C3418 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3418"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3418"
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# コンパイラ エラー C3418
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アクセス指定子 'specifier' はサポートされていません  
  
 CLR アクセス指定子が正しく指定されていません。  詳細については、「[型およびメンバーの可視性](../Topic/Type%20and%20Member%20Visibility.md)」を参照してください。  
  
## 使用例  
 次の例では C3418 が生成されます。  
  
```  
// C3418.cpp // compile with: /clr /c ref struct m { internal public:   // C3418 void test(){} }; ref struct n { internal:   // OK void test(){} };  
```