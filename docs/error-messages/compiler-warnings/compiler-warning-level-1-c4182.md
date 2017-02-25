---
title: "コンパイラの警告 (レベル 1) C4182 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4182"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4182"
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4182
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#include の入れ子のレベルの深さは 'number' です。無限再帰の可能性があります  
  
 コンパイラがヒープ上の領域を使い切りました。入れ子になっているインクルード ファイルの数が原因です。 インクルード ファイルは、別のインクルード ファイルに含められると入れ子になります。  
  
 このメッセージは情報目的で、エラー [C1076](../Topic/Fatal%20Error%20C1076.md) に先だって表示されます。