---
title: "符号付きビット処理演算 | Microsoft Docs"
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
  - "ビット処理演算"
  - "符号付きビット処理演算"
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 符号付きビット処理演算
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3** 符号付き整数のビットごとの演算の結果  
  
 符号付き整数のビットごとの演算は、符号なし整数のビットごとの演算と同じように動作します。  たとえば、`–16 & 99` は、バイナリでは次のように表されます。  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 ビットごとの AND の結果は 96 です。  
  
## 参照  
 [整数](../Topic/Integers.md)