---
title: "変換演算子のみが &#39;&lt;keyword&gt;&#39; として宣言できます。 | Microsoft Docs"
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
  - "bc33019"
  - "vbc33019"
helpviewer_keywords: 
  - "BC33019"
ms.assetid: 946266fe-a909-41b1-aad4-f85dc8050b88
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 変換演算子のみが &#39;&lt;keyword&gt;&#39; として宣言できます。
演算子が変換演算子でない場合に、[Operator Statement](../Topic/Operator%20Statement.md) が [Widening](../Topic/Widening%20\(Visual%20Basic\).md) または [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md) を指定しています。  
  
 すべての演算子は、[Public](../Topic/Public%20\(Visual%20Basic\).md) と [Shared](../Topic/Shared%20\(Visual%20Basic\).md) の両方として宣言する必要があります。 ただし、変換演算子だけは [Widening](../Topic/Widening%20\(Visual%20Basic\).md) または [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md) で宣言できますが、両方で宣言することはできません。  
  
 演算子の定義には、必要に応じて、[Overloads](../Topic/Overloads%20\(Visual%20Basic\).md) と [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md) のキーワードを含めることができます。 その他のキーワードは [Operator Statement](../Topic/Operator%20Statement.md) では許可されません。  
  
 **エラー ID:** BC33019  
  
### このエラーを解決するには  
  
1.  演算子の定義から `Widening` または `Narrowing` キーワードを削除します。 型変換が行われていないため、これらは適用されません。  
  
## 参照  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Type Conversions in Visual Basic](../Topic/Type%20Conversions%20in%20Visual%20Basic.md)