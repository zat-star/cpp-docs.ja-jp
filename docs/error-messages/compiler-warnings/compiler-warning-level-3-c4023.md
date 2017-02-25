---
title: "コンパイラの警告 (レベル 3) C4023 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4023"
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 3) C4023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : \_based ポインターがプロトタイプ宣言されていない関数へ渡されます : パラメーター番号  
  
 プロトタイプ宣言されていない関数に \_based ポインターを渡すと、ポインターが正規化され、予期しない結果になります。  
  
 \_based ポインターを渡されるプロトタイプ関数を使用すると、この警告が解決することがあります。