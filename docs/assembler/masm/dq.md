---
title: "DQ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DQ"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DQ directive"
ms.assetid: 15de9c41-db90-4bca-affc-426eeb38ebc0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DQ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

各 `initializer` の領域の 8 バイトを割り当て必要に応じて初期化します。  また、型が適正である場合は、型指定子としても使用できます。  `DQ` は [QWORD](../../assembler/masm/qword.md) のシノニムです。  
  
## 構文  
  
```  
[[name]] DQ initializer [[, initializer]]...  
```  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [QWORD](../../assembler/masm/qword.md)