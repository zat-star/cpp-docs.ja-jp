---
title: "&lt;type1&gt; &#39;&lt;propertyname&gt;&#39; が、基本クラスである &lt;type2&gt;  &#39;&lt;classname&gt;&#39; のイベント &#39;&lt;eventname&gt;&#39; に対して暗黙的に宣言されたメンバーと競合しています | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40014"
  - "bc40014"
helpviewer_keywords: 
  - "BC40014"
ms.assetid: 100534b9-d533-4e94-a2a7-0ed26426965b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type1&gt; &#39;&lt;propertyname&gt;&#39; が、基本クラスである &lt;type2&gt;  &#39;&lt;classname&gt;&#39; のイベント &#39;&lt;eventname&gt;&#39; に対して暗黙的に宣言されたメンバーと競合しています
プロパティが、基底クラスのイベントから形成された暗黙的なメンバーと同じ名前で宣言されています。 たとえば、基底クラスに `Event1` という名前のイベントが定義されている場合、コンパイラは暗黙的なプロシージャ `add_Event1` と `remove_Event1` を生成します。 このクラスのプロパティがこれらの名前のいずれかである場合は、基底クラスのメンバーをシャドウする必要があります。  
  
 このメッセージは警告です。`Shadows` は、既定で指定されていると見なされます。 警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md)」を参照してください。  
  
 **エラー ID:** BC40014  
  
### このエラーを解決するには  
  
1.  基底クラスのメンバーを非表示にするには、プロパティ宣言に `Shadows` キーワードを追加します。  
  
2.  基底クラスのメンバーを非表示にしない場合は、プロパティ名を変更します。  
  
## 参照  
 [Property Statement](../Topic/Property%20Statement.md)   
 [Event Statement](../Topic/Event%20Statement.md)   
 [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)   
 [Shadowing in Visual Basic](../Topic/Shadowing%20in%20Visual%20Basic.md)