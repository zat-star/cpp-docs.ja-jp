---
title: "INSTR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "InStr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INSTR directive"
ms.assetid: fc37f6a2-3c95-47b2-b6bb-1066edd25994
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# INSTR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*textitem1* の *textitem2* の最初の出現箇所を検索します。  
  
## 構文  
  
```  
  
name  
 INSTR [[position,]] textitem1, textitem2  
```  
  
## 解説  
 開始位置は省略可能です。  テキストの各項目はリテラル文字列`%` を指定する定数またはマクロ関数によって返される文字列のいずれかになります。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)