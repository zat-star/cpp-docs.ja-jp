---
title: "メソッドに &#39;On Error GoTo&#39; ステートメントとラムダ式またはクエリ式の両方を含めることはできません | Microsoft Docs"
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
  - "bc36595"
  - "vbc36595"
helpviewer_keywords: 
  - "BC36595"
ms.assetid: 4e7cc11e-f53d-4481-afb4-653a81d54483
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# メソッドに &#39;On Error GoTo&#39; ステートメントとラムダ式またはクエリ式の両方を含めることはできません
1 つのメソッドに、`On Error Goto` ステートメントと、ラムダ式または LINQ クエリのどちらかが含まれています。 1 つのメソッドには、`On Error Goto` ステートメントとともに、ラムダ式や LINQ クエリを含めることはできません。  
  
 **エラー ID:** BC36595  
  
### このエラーを解決するには  
  
1.  `On Error Goto` ステートメントを使用する例外処理コードを `Try...Catch` ステートメントに置き換えてください。  
  
## 参照  
 [例外処理の概要 \(Visual Basic\)](http://msdn.microsoft.com/ja-jp/9792f16a-0cd2-40bd-ace2-f7a4344c0e52)   
 [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [Lambda Expressions](../Topic/Lambda%20Expressions%20\(Visual%20Basic\).md)   
 [On Error Statement](../Topic/On%20Error%20Statement%20\(Visual%20Basic\).md)