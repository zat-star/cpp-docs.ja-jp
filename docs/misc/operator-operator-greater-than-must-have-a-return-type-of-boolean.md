---
title: "演算子 &#39;&lt;operator&gt;&#39; には、ブール型の戻り値の型を指定しなければなりません | Microsoft Docs"
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
  - "vbc33023"
  - "bc33023"
helpviewer_keywords: 
  - "BC33023"
ms.assetid: 18e066f4-d71e-4e38-b0bc-8af9145f6015
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 演算子 &#39;&lt;operator&gt;&#39; には、ブール型の戻り値の型を指定しなければなりません
比較演算子または論理演算子が、[Boolean Data Type](../Topic/Boolean%20Data%20Type%20\(Visual%20Basic\).md) 以外の戻り値の型で宣言されています。  
  
 比較演算子 \(`=`、`<>`、`<`、`<=`、`>`、`>=`、`Is`、`IsNot`、`IsFalse`、`IsTrue`、`Like`、`TypeOf`\) の結果として使用できるのは、`True` または `False` のみです。 詳細については、「[Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)」を参照してください。  
  
 論理演算子 \(`And`、`AndAlso`、`Not`、`Or`、`OrElse`、`Xor`\) は、ブール値のドメイン内でのみ機能します。 詳細については、「[Logical and Bitwise Operators in Visual Basic](../Topic/Logical%20and%20Bitwise%20Operators%20in%20Visual%20Basic.md)」を参照してください。  
  
 **エラー ID:** BC33023  
  
### このエラーを解決するには  
  
-   この比較演算子または論理演算子の戻り値の型を `Boolean` に置き換えてください。  
  
## 参照  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)