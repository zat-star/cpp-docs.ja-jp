---
title: "型変換 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1e4dede1dab1fcaf9ae4de5846539924d0095e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="type-conversions-c"></a>型変換 (C)
型変換は、指定された演算子と、オペランドまたは演算子の型に依存します。 次の場合に型変換が実行されます。  
  
-   ある型の値が異なる型の変数に代入されるとき、または演算子が演算を実行する前にオペランドの型を変換するとき  
  
-   ある型の値が異なる型に明示的にキャストされるとき  
  
-   値が関数に引数として渡されるとき、または型が関数から戻されるとき  
  
 文字、短整数、整数ビット フィールド (符号付きと符号なし)、または列挙型のオブジェクトは、整数が使用できる場所であれば式内のどこででも使用できます。 `int` が元の型のすべての値を表すことができる場合、値は `int` に変換されます。それ以外の場合は `unsigned int` に変換されます。 このプロセスを "整数の上位変換" といいます。 整数の上位変換では値が保持されます。 つまり、上位変換後の値が上位変換前と同じであることが保証されます。 詳細については、「[通常の算術変換](../c-language/usual-arithmetic-conversions.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [式と代入](../c-language/expressions-and-assignments.md)