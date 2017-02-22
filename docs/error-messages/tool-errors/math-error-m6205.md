---
title: "数値演算エラー M6205 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6205"
ms.assetid: fd28e7c9-a463-4a9c-a863-cc9e75315550
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 数値演算エラー M6205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : \_TLOSS エラー  
  
 許容範囲を超えて精度が低下しています。  
  
 このエラーは、sin、cos、tan のオペランドに大きすぎる値を指定した時に発生します。これらの関数では、三角関数の計算の前に、オペランドが 0 以上 2\*pi 以内に減少される必要があります。