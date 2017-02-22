---
title: "コンパイラ エラー C2410 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2410"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2410"
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C2410
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'context' 内にあいまいなメンバー名があります。  
  
 この識別子は、指定されたコンテキストの複数の構造体または共用体のメンバーです。  
  
 エラーを起こしたオペランドに構造体指定子または共用体指定子を付けてください。  構造体指定子や共用体指定子に使用できるのは、`struct` 型または `union` 型の識別子 \(参照される構造体または共用体と同じ型の `typedef` 名または変数\) です。  エラーを起こしたオペランドを使用するには、指定子を最初のメンバー選択演算子 \(.\) の左側のオペランドにしてください。