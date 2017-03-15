---
title: "コンパイラの警告 (レベル 3) C4013 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4013"
ms.assetid: 9f9afc71-6e78-463d-9d66-3012d6a3cd5d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 3) C4013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数 'function' は定義されていません。int 型の値を返す外部関数と見なします。  
  
 コンパイラで未定義の関数の呼び出しが検出されました。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  関数名のスペルが間違っています。  
  
2.  外部関数が `extern` としてプロトタイプ宣言されていません。