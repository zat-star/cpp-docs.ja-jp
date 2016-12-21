---
title: "整数の浮動小数点値へのキャスト | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "整数, 浮動小数点値へのキャスト"
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 整数の浮動小数点値へのキャスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.2.1.3** 整数を、元の値を正確に表現できない浮動小数点数に変換する場合の切り捨てまたは丸めの方向  
  
 整数を、元の値を正確に表現できない浮動小数点数値にキャストすると、最も近い適切な値に切り上げまたは切り下げられます。  
  
 たとえば、**unsigned long** \(32 ビット精度\) を **float** \(仮数が 23 ビット精度\) にキャストすると、最も近い 256 の倍数に丸められます。  **long** 値 4,294,966,913 ～ 4,294,967,167 はすべて **float** 値 4,294,967,040 に丸められます。  
  
## 参照  
 [浮動小数点数値演算](../c-language/floating-point-math.md)