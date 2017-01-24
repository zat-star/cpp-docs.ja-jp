---
title: "&lt;type1&gt; &#39;&lt;membername&gt;&#39; は、基底クラス &lt;type3&gt; &#39;&lt;classname&gt;&#39; の &lt;type2&gt; &#39;&lt;membername&gt;&#39; と競合しており、&#39;Shadows&#39; と宣言する必要があります | Microsoft Docs"
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
  - "bc40004"
  - "vbc40004"
helpviewer_keywords: 
  - "BC40004"
ms.assetid: 24d10f31-3b3d-448c-b928-fc937e1f4a92
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type1&gt; &#39;&lt;membername&gt;&#39; は、基底クラス &lt;type3&gt; &#39;&lt;classname&gt;&#39; の &lt;type2&gt; &#39;&lt;membername&gt;&#39; と競合しており、&#39;Shadows&#39; と宣言する必要があります
プログラミング要素が、基底クラスで定義された要素と同じ名前で宣言されています。 この場合、このクラスの要素は、基底クラス要素をシャドウする必要があります。  
  
 このメッセージは警告です。`Shadows` は、既定で指定されているとみなされます。 警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md)」を参照してください。  
  
 **エラー ID:** BC40004  
  
### このエラーを解決するには  
  
-   `Shadows` キーワードを宣言に追加するか、宣言される要素の名前を変更します。  
  
## 参照  
 [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)   
 [Shadowing in Visual Basic](../Topic/Shadowing%20in%20Visual%20Basic.md)