---
title: "NMAKE の致命的なエラー U1001 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1001"
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

構文エラー : 無効な文字 'character' がマクロ中にあります。  
  
 マクロの中に英数字でもアンダースコア \(**\_**\) でもない文字があります。  
  
 このエラーは、マクロの展開でコロンがないことが原因で発生する場合があります。  
  
```  
syntax error : illegal character '=' in macro  
```