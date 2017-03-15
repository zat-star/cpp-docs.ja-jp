---
title: "関数呼び出しでの変換 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "関数呼び出し, 引数の型変換"
  - "関数呼び出し, 変換"
  - "関数 [C], 引数の変換"
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 関数呼び出しでの変換
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数呼び出しの引数に対して実行される変換の種類は、呼び出される関数の宣言された引数の型を持つ関数プロトタイプ \(事前宣言\) の有無によって異なります。  
  
 関数プロトタイプがあり、その関数プロトタイプに宣言された引数の型が含まれている場合、コンパイラは型チェックを実行します \(「[関数](../Topic/Functions%20\(C\).md)」を参照\)。  
  
 関数プロトタイプがない場合、関数呼び出しの引数に対しては通常の算術変換だけが実行されます。  これらの変換は呼び出しの各引数に対して個別に実行されます。  つまり、**float** 値は **double** に変換され、`char` または **short** 値は `int` に変換され、`unsigned char` または **unsigned short** は `unsigned int` に変換されます。  
  
## 参照  
 [型変換](../c-language/type-conversions-c.md)