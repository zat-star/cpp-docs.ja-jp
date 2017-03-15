---
title: "整数値の範囲 | Microsoft Docs"
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
ms.assetid: 0e9c6161-8f3f-4bfb-9fcc-a6c8dc97d702
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 整数値の範囲
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.1.2.5** 整数のさまざまな型の表現と値セット  
  
 整数は 32 ビット \(4 バイト\) を含みます。  符号付き整数は、2 の補数形式で表されます。  最上位ビットは符号を表し、負の数ならば 1、正の数とゼロならば 0 です。  値は次のとおりです。  
  
|型|最小および最大|  
|-------|-------------|  
|**unsigned short**|0 ～ 65535|  
|`signed short`|\-32768 ～ 32767|  
|`unsigned long`|0 ～ 4294967295|  
|**signed long**|–2147483648 ～ 2147483647|  
  
## 参照  
 [整数](../Topic/Integers.md)