---
title: "XML コメント タグ &#39;returns&#39; は、&#39;declare sub&#39; 言語要素では許可されていません | Microsoft Docs"
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
  - "bc42315"
  - "vbc42315"
helpviewer_keywords: 
  - "BC42315"
ms.assetid: 55ba3e8a-ba7f-42e3-a4a7-b22844e72564
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML コメント タグ &#39;returns&#39; は、&#39;declare sub&#39; 言語要素では許可されていません
XML コメント タグ 'returns' は、'declare sub' 言語要素では許可されていません。 XML コメントは無視されます。  
  
 `Declare Sub` 宣言に対する XML コメントに、`<`returns`>` タグを含めることはできません。  
  
 **エラー ID:** BC42315  
  
### このエラーを解決するには  
  
-   サポートされていない `<`returns`>` タグを削除します。  
  
## 参照  
 [\<returns\>](../Topic/%3Creturns%3E%20\(Visual%20Basic\).md)   
 [XML Comment Tags](../Topic/Recommended%20XML%20Tags%20for%20Documentation%20Comments%20\(Visual%20Basic\).md)   
 [Documenting Your Code with XML](../Topic/Documenting%20Your%20Code%20with%20XML%20\(Visual%20Basic\).md)   
 [Declare Statement](../Topic/Declare%20Statement.md)