---
title: "推論規則の優先順位 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "推論規則 (NMAKE の)"
  - "優先順位, 推論規則"
  - "規則, 推論"
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 推論規則の優先順位
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

推論規則が重複して定義されている場合、NMAKE は優先順位の最も高い定義を使用します。  推論規則の優先順位は次のとおりです。  
  
1.  メイクファイルで定義されている推論規則。複数の定義では、後で定義されている方が優先されます。  
  
2.  Tools.ini で定義されている推論規則。複数の定義では、後で定義されている方が優先されます。  
  
3.  定義済み推論規則。  
  
## 参照  
 [推論規則](../build/inference-rules.md)