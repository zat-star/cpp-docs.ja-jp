---
title: "コンパイラ エラー C3551 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3551"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3551"
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3551
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"遅延指定の戻り値の型が必要です"  
  
 関数の戻り値の型のプレース ホルダーとして `auto` キーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 次の例では、関数 `myFunction` の遅延指定の戻り値の型は、型 `int` の 4 つの要素の配列へのポインターです。  
  
```  
auto myFunction()->int(*)[4];   
```  
  
## 参照  
 [auto](../../cpp/auto-cpp.md)