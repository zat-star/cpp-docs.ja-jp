---
title: "型引数は式 &#39;&lt;expression&gt;&#39; に適用できません | Microsoft Docs"
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
  - "bc32058"
  - "vbc32058"
helpviewer_keywords: 
  - "BC32058"
ms.assetid: c6b9b49c-6fb2-47b8-a8bb-464562d3adfd
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 型引数は式 &#39;&lt;expression&gt;&#39; に適用できません
インポート エイリアスが、そのインポート エイリアスに型引数を渡す [Of](../Topic/Of%20Clause%20\(Visual%20Basic\).md) 句で定義されています。  
  
 型引数はジェネリック型で使用されるものであり、ジェネリック型になり得るのは、クラス、構造体、インターフェイス、プロシージャ、デリゲートのみです。 名前空間やインポート エイリアスはジェネリックになりません。  
  
 **エラー ID:** BC32058  
  
### このエラーを解決するには  
  
-   `Of` 句と型引数をインポート エイリアスから削除します。  
  
## 参照  
 [Imports Statement \(.NET Namespace and Type\)](../Topic/Imports%20Statement%20\(.NET%20Namespace%20and%20Type\).md)   
 [References and the Imports Statement](../Topic/References%20and%20the%20Imports%20Statement%20\(Visual%20Basic\).md)   
 [ビルド内にありません: 同じ名前を持つ複数の変数がある場合に参照を解決する](http://msdn.microsoft.com/ja-jp/9601e39f-1911-44e1-ace5-3f6e090408b9)   
 [Visual Basic におけるジェネリック型](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)