---
title: "__based 文法 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ベース アドレス指定"
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __based 文法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 ベースとなるアドレス指定は、オブジェクトが割り当てられるセグメントを詳細に制御する必要がある場合に便利です \(静的および動的ベースのデータ\)。  
  
 32 ビットおよび 64 ビット コンパイルで受け入れられるベースとなるアドレス指定の唯一の形式は、32 ビットまたは 64 ビット ベースへの 32 ビットまたは 64 ビットの変位を含む型を定義する、または `void` に基づく、「ポインターをベースとする」ものです。  
  
## 文法  
 *based\-range\-modifier*:  
 **\_\_based\(**  *base\-expression*  **\)**  
  
 *base\-expression*:  
 *based\-variablebased\-abstract\-declaratorsegment\-namesegment\-cast*  
  
 *based\-variable*:  
 *identifier*  
  
 *based\-abstract\-declarator*:  
 *abstract\-declarator*  
  
 *base\-type*:  
 *type\-name*  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [ベース ポインター](../Topic/Based%20Pointers%20\(C++\).md)