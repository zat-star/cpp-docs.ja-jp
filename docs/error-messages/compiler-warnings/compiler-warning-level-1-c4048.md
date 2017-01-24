---
title: "コンパイラの警告 (レベル 1) C4048 | Microsoft Docs"
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
  - "C4048"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4048"
ms.assetid: 8429f513-4732-40f1-8e56-4c224e723bcb
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4048
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier1' と 'identifier2' で宣言された配列添字が異なります。  
  
 複数のポインターが使用されている式で、ポインターの指している配列のサイズが異なっています。  ポインターは変換されずに使用されます。  
  
 この警告は、配列を同じ型または等価の型に明示的にキャストすると解決することがあります。