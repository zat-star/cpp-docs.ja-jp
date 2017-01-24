---
title: "単純な代入 (C) | Microsoft Docs"
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
  - "代入演算子 [C++], 単純な"
  - "データ型変換 [C++], 単純な代入"
  - "等号"
  - "演算子 [C], 単純な代入"
  - "単純な代入演算子"
  - "型変換 [C++], 単純な代入"
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 単純な代入 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

単純な代入演算子は左オペランドに右オペランドを代入します。  右オペランドの値は、代入式の型に変換され、左オペランドで指定されたオブジェクトに格納されている値を置き換えます。  代入の変換規則が適用されます \(「[代入の変換](../c-language/assignment-conversions.md)」を参照\)。  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 この例では、`y` の値は **double** 型に変換され、`x` に割り当てます。  
  
## 参照  
 [C 代入演算子](../c-language/c-assignment-operators.md)