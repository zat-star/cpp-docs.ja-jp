---
title: "致命的なエラー C1054 | Microsoft Docs"
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
  - "C1054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1054"
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの制限 : 初期化子の入れ子のレベルが深すぎます。  
  
 コードの初期化子の入れ子が制限値 \(10 ～ 15 レベル。初期化される型の組み合わせによって異なります\) を超えています。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  初期化されるデータ型を簡単にして、入れ子を減らします。  
  
2.  宣言の後に別のステートメントで変数を初期化します。