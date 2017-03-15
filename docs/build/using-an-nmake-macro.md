---
title: "NMAKE マクロの使用 | Microsoft Docs"
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
  - "マクロ, NMAKE"
  - "NMAKE マクロ, 使用"
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# NMAKE マクロの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マクロを使用するには、次の構文のように名前をかっこで囲み、先頭にドル記号 \($\) を配置します。  
  
## 構文  
  
```  
$(macroname)  
```  
  
## 解説  
 空白を入れることはできません。  *macroname* が 1 文字の場合は、かっこを省略できます。  $\(*macroname*\) は、定義文字列で置換されます。未定義マクロは、null 文字列で置換されます。  
  
## さらに詳しくは次のトピックをクリックしてください  
 [マクロでの代入](../build/macro-substitution.md)  
  
## 参照  
 [マクロと NMAKE](../Topic/Macros%20and%20NMAKE.md)