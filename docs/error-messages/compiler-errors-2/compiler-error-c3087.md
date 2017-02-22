---
title: "コンパイラ エラー C3087 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3087"
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# コンパイラ エラー C3087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'named\_argument': 'attribute' の呼び出しは、既にこのメンバーを初期化しています  
  
 名前付き引数が、同じ値の名前なし引数と同じ属性ブロックに指定されました。 名前付引数か名前なし引数の、どちらか 1 つだけを指定します。  
  
## 使用例  
 次の例では C3087 が生成されます。  
  
```  
// C3087.cpp // compile with: /c [idl_quote("quote1", text="quote2")];   // C3087 [idl_quote(text="quote3")];   // OK [idl_quote("quote4")];   // OK  
```