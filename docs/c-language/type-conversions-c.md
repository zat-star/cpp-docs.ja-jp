---
title: "型変換 (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "変換, 型"
  - "変換 (型を)"
  - "整数の上位変換"
  - "型キャスト, 実行時"
  - "型変換"
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 型変換 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型変換は、指定された演算子と、オペランドまたは演算子の型に依存します。  次の場合に型変換が実行されます。  
  
-   ある型の値が異なる型の変数に代入されるとき、または演算子が演算を実行する前にオペランドの型を変換するとき  
  
-   ある型の値が異なる型に明示的にキャストされるとき  
  
-   値が関数に引数として渡されるとき、または型が関数から戻されるとき  
  
 文字、短整数、整数ビット フィールド \(符号付きと符号なし\)、または列挙型のオブジェクトは、整数が使用できる場所であれば式内のどこででも使用できます。  `int` が元の型のすべての値を表すことができる場合、値は `int` に変換されます。それ以外の場合は `unsigned int` に変換されます。  このプロセスを "整数の上位変換" といいます。 整数の上位変換では値が保持されます。  つまり、上位変換後の値が上位変換前と同じであることが保証されます。  詳細については、「[Usual Arithmetic Conversions \(通常の算術変換\)](../c-language/usual-arithmetic-conversions.md)」を参照してください。  
  
## 参照  
 [式と割り当て](../c-language/expressions-and-assignments.md)