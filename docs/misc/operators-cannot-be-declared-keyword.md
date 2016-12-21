---
title: "演算子は &#39;&lt;keyword&gt;&#39; として宣言できません | Microsoft Docs"
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
  - "vbc33013"
  - "bc33013"
helpviewer_keywords: 
  - "BC33013"
ms.assetid: bfd805f4-e30e-4553-9cb7-2690595f0480
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 演算子は &#39;&lt;keyword&gt;&#39; として宣言できません
演算子が、演算子の定義に使用できないキーワードを使用して宣言されています。  
  
 すべての演算子は、[Public](../Topic/Public%20\(Visual%20Basic\).md) と [Shared](../Topic/Shared%20\(Visual%20Basic\).md) の両方として宣言する必要があります。 さらに、変換演算子は [Widening](../Topic/Widening%20\(Visual%20Basic\).md) か [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md) のいずれかを使用して宣言する必要があり、両方を使用することはできません。 演算子の定義には、必要に応じて、[Overloads](../Topic/Overloads%20\(Visual%20Basic\).md) または [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md) のキーワードを含めることができます。 その他のキーワードは [Operator Statement](../Topic/Operator%20Statement.md) では許可されません。  
  
 **エラー ID:** BC33013  
  
### このエラーを解決するには  
  
-   使用できないキーワードを演算子の定義から削除します。  
  
## 参照  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)