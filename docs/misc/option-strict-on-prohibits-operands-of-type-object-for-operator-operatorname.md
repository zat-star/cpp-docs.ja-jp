---
title: "Option Strict On では、演算子 &#39;&lt;operatorname&gt;&#39; に対して Object 型のオペランドを使用することはできません。 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30038"
  - "vbc30038"
helpviewer_keywords: 
  - "BC30038"
ms.assetid: eb047d36-1fb4-460d-ae98-c76f31a89bed
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On では、演算子 &#39;&lt;operatorname&gt;&#39; に対して Object 型のオペランドを使用することはできません。
オブジェクト変数に定義されている演算子は `Is` と `TypeOf...Is` だけです。`Option Strict` が `On` である場合、すべてのオペランドは、指定した演算子で定義されているデータ型である必要があります。  
  
 **エラー ID:** BC30038  
  
### このエラーを解決するには  
  
-   `CInt` や `CStr` などの適切な型変換関数を使用して、演算子について定義されたデータ型にオペランドを変換します。  
  
## 参照  
 [Is Operator](../Topic/Is%20Operator%20\(Visual%20Basic\).md)   
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)   
 [Type Conversion Functions](../Topic/Type%20Conversion%20Functions%20\(Visual%20Basic\).md)