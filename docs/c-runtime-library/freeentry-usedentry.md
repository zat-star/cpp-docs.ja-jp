---
title: "_FREEENTRY、_USEDENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "USEDENTRY"
  - "_USEDENTRY"
  - "_FREEENTRY"
  - "FREEENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_FREEENTRY 定数"
  - "_USEDENTRY 定数"
  - "FREEENTRY 定数"
  - "USEDENTRY 定数"
ms.assetid: 26f658e6-6846-4a4e-9984-262cfe392770
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _FREEENTRY、_USEDENTRY
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
#include <malloc.h>  
```  
  
## 解説  
 これらの定数は **\_HEAPINFO** 構造体の **\_useflag** 要素に `_heapwalk` ルーチンに割り当てられた値を表します。  これらはヒープ エントリの状態を示します。  
  
## 参照  
 [\_heapwalk](../Topic/_heapwalk.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)