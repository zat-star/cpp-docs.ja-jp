---
title: "コンパイラ エラー C2995 | Microsoft Docs"
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
  - "C2995"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2995"
ms.assetid: a57cdfe0-b40b-4a67-a95c-1a49ace4842b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2995
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 関数テンプレートは既に定義されています  
  
 テンプレート クラスの各メンバー関数の定義は 1 つのみであることを確認します。  
  
 次の例では C2995 が生成されます。  
  
```  
// C2995.cpp // compile with: /c template <class T> void Test(T x){} template <class T> void Test(T x){}   // C2995 template <class T> void Test2(T x){}   // OK  
```