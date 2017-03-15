---
title: "致命的なエラー C1026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1026"
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 致命的なエラー C1026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムの解析でコンパイラ内でスタック オーバーフローが発生しました。プログラムが複雑すぎます。  
  
 プログラムの解析に必要な領域でコンパイラのスタック オーバーフローが発生しました。  
  
 以下のいずれかの方法で式を簡単にしてください。  
  
-   `for` ステートメントや `switch` ステートメントの入れ子を減らします。  さらに深い入れ子があるステートメントは、別の関数に分割します。  
  
-   コンマ演算子や関数呼び出しを含む長い式を分割します。