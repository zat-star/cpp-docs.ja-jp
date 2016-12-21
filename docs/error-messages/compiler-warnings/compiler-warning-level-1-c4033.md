---
title: "コンパイラの警告 (レベル 1) C4033 | Microsoft Docs"
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
  - "C4033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4033"
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 値を返さなければいけません  
  
 この関数は値を返しません。 定義されていない値が返されます。  
  
 戻り値のない `return` を使用する関数は、型 `void` として宣言する必要があります。  
  
 このエラーは、C 言語コード用です。  
  
 次の例では C4033 が生成されます。  
  
```  
// C4033.c // compile with: /W1 /LD int test_1(int x)   // C4033 expected { if (x) { return;   // C4033 } }  
```