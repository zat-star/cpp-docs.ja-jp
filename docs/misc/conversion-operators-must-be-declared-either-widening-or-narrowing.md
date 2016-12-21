---
title: "変換演算子は、&#39;Widening&#39; または &#39;Narrowing&#39; のいずれかとして宣言されなければなりません | Microsoft Docs"
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
  - "vbc33017"
  - "bc33017"
helpviewer_keywords: 
  - "BC33017"
ms.assetid: 5972d955-ce1d-4348-a021-167eecb3a507
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 変換演算子は、&#39;Widening&#39; または &#39;Narrowing&#39; のいずれかとして宣言されなければなりません
[Operator Statement](../Topic/Operator%20Statement.md) に、[Widening](../Topic/Widening%20\(Visual%20Basic\).md) も [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md) も指定されていません。  
  
 変換演算子を定義するときは、`Widening` または `Narrowing` のいずれかとして宣言する必要があります。 これらは相互に排他的な特性であるため、両方を指定することはできません。  
  
 **エラー ID:** BC33017  
  
### このエラーを解決するには  
  
-   変換演算子を `Widening` と `Narrowing` のどちらにするかを決定し、`Operator` ステートメントに正しいキーワードを含めます。 どちらか一方を指定する必要があります。  
  
## 参照  
 [Widening and Narrowing Conversions](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)   
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)