---
title: "ジェネリック メソッドを COM に公開できません | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30943"
  - "bc30943"
helpviewer_keywords: 
  - "BC30943"
ms.assetid: 0e3bff62-f187-4864-8520-70f6be22e869
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ジェネリック メソッドを COM に公開できません
1 つ以上のジェネリック プロシージャが含まれている [!INCLUDE[dnprdnshort](../Token/dnprdnshort_md.md)] コンポーネントが COM コンポーネントにエクスポートされます。  
  
 コンポーネント オブジェクト モデル \(COM\) では、ジェネリック型をサポートしていないため、相互運用できません。  
  
 **エラー ID:** BC30943  
  
### このエラーを解決するには  
  
-   [!INCLUDE[dnprdnshort](../Token/dnprdnshort_md.md)] コンポーネントから 1 つ以上のジェネリック プロシージャを削除するか、そのコンポーネントを COM 相互運用に使用しないでください。  
  
## 参照  
 [Visual Basic におけるジェネリック型](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [COM Interop](../Topic/COM%20Interop%20\(Visual%20Basic\).md)