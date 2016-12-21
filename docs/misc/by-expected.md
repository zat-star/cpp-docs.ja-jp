---
title: "&#39;By&#39; が必要です。 | Microsoft Docs"
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
  - "vbc36605"
  - "bc36605"
helpviewer_keywords: 
  - "BC36605"
ms.assetid: d0397b6e-bfc2-400c-92fc-efe82036cfdb
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;By&#39; が必要です。
`Order By` または `Group By` 句が指定されていますが、`By` キーワードがありません。  
  
 **エラー ID:** BC36605  
  
### このエラーを解決するには  
  
1.  `By` キーワードを `Order By` または `Group By` 句に追加します。 次に例を示します。  
  
    ```vb#  
    Dim customersByCountry = From cust In customers _  
                             Order By cust.Country, cust.City _  
                             Group By CountryName = cust.Country _  
                             Into RegionalCustomers = Group, Count() _  
                             Order By CountryName  
    ```  
  
## 参照  
 [How to: Sort Query Results](../Topic/How%20to:%20Sort%20Query%20Results%20by%20Using%20LINQ%20\(Visual%20Basic\).md)   
 [Order By Clause](../Topic/Order%20By%20Clause%20\(Visual%20Basic\).md)   
 [Group By 句](../Topic/Group%20By%20Clause%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)