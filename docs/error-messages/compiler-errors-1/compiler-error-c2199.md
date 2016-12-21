---
title: "コンパイラ エラー C2199 | Microsoft Docs"
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
  - "C2199"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2199"
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2199
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

構文エラー : グローバル スコープで 'identifier \(' が見つかりました。  
  
 指定されたコンテキストに構文エラーが発生しました。  宣言の構文が間違っている可能性があります。  
  
 次の例では警告 C2199 が生成されます。  
  
```  
// C2199.cpp  
// compile with: /c  
int j = int(1) int(1);   // C2199  
int j = 1;   // OK  
```