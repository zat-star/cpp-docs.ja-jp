---
title: "CLOCKS_PER_SEC、CLK_TCK | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLOCKS_PER_SEC"
  - "CLK_TCK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLK_TCK 定数"
  - "CLOCKS_PER_SEC"
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# CLOCKS_PER_SEC、CLK_TCK
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <time.h>  
```  
  
## 解説  
 秒単位の時間は `CLOCKS_PER_SEC`で除算 `clock` 関数によって返される値です。  `CLK_TCK` は 同じですが、Obsolete と考慮されます。  
  
## 参照  
 [clock](../c-runtime-library/reference/clock.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)