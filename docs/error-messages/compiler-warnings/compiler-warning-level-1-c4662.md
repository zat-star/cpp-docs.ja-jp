---
title: "コンパイラの警告 (レベル 1) C4662 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4662"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4662"
ms.assetid: 7efda273-d04a-47b7-ad65-ff1ff94b5ffc
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# コンパイラの警告 (レベル 1) C4662
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

明示的なインスタンス化。テンプレート クラス 'identifier1' に 'identifier2' を特定する定義がありません  
  
 指定したテンプレート クラスを宣言しましたが、定義していません。  
  
## 使用例  
  
```  
// C4662.cpp // compile with: /W1 /LD template<class T, int i> class MyClass; // no definition template MyClass< int, 1>;              // C4662  
```