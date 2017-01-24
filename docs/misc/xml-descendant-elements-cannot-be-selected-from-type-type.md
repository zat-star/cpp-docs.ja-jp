---
title: "XML 子孫要素を型 &#39;type&#39; から選択することはできません | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36809"
  - "bc36809"
helpviewer_keywords: 
  - "BC36809"
ms.assetid: 560a3370-f24d-4ca3-93b1-39aabe13c238
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 子孫要素を型 &#39;type&#39; から選択することはできません
型が <xref:System.Xml.Linq.XElement>、<xref:System.Xml.Linq.XDocument>、または`IEnumerable(Of XElement)` のいずれでもないオブジェクトで XML 子孫が参照されています。 詳細については、「[XML Descendant Axis Property](../Topic/XML%20Descendant%20Axis%20Property%20\(Visual%20Basic\).md)」を参照してください。  
  
```vb#  
' Generates an error. Dim var = "sample text"...<childElement>  
```  
  
 **エラー ID:** BC36809  
  
### このエラーを解決するには  
  
-   子孫要素を参照しているオブジェクトが、<xref:System.Xml.Linq.XElement>、<xref:System.Xml.Linq.XDocument>、または `IEnumerable(Of XElement)` のいずれかとして厳密に型指定されていることを確認してください。 例を次に示します。  
  
    ```vb#  
    Dim elem As XElement = <root> <child /> </root> Dim var = elem...<child>  
    ```  
  
## 参照  
 [XML Descendant Axis Property](../Topic/XML%20Descendant%20Axis%20Property%20\(Visual%20Basic\).md)   
 [XML Axis Properties](../Topic/XML%20Axis%20Properties%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)