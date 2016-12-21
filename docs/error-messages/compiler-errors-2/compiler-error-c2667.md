---
title: "コンパイラ エラー C2667 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2667"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2667"
ms.assetid: 3c91d9d1-18fa-4e0d-a9ba-984d38980ca3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2667
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : number 個のオーバーロード関数があいまいで最適な変換ができません。  
  
 オーバーロードされた関数の呼び出しがあいまいで、解決できません。  
  
 関数呼び出しの実パラメーターをオーバーロードされた関数の 1 つに適合させるために必要な変換は、その他のすべてのオーバーロードされた関数で必要とされる変換よりも厳密である必要があります。  
  
 関数テンプレートの一部の順序付けの詳細については、Knowledge Base 文書の「BUG: C2667 and C2668 on Partial Ordering of Function Templates \(Q240869\)」を参照してください。