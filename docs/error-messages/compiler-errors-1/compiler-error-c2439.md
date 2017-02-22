---
title: "コンパイラ エラー C2439 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2439"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2439"
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C2439
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 指定されたメンバーは初期化できません。  
  
 クラス、構造体、または共用体のメンバーは初期化できません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  間接基本クラスまたは構造体の初期化を試みました。  
  
2.  クラスまたは構造体の継承されたメンバーの初期化を試みました。  継承されたメンバーはクラスや構造体のコンストラクターで初期化する必要があります。