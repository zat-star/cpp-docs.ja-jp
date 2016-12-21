---
title: "setvbuf 定数 | Microsoft Docs"
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
  - "_IOFBF"
  - "_IONBF"
  - "_IOLBF"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_IOFBF 定数"
  - "_IOLBF 定数"
  - "_IONBF 定数"
  - "IOFBF 定数"
  - "IOLBF 定数"
  - "IONBF 定数"
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# setvbuf 定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <stdio.h>  
  
```  
  
## 解説  
 これらの定数は `setvbuf`のバッファーの種類を表します。  
  
 有効値は、次の記号定数で指定します:  
  
|定数|説明|  
|--------|--------|  
|`_IOFBF`|フル バッファリング。: `setvbuf` の呼び出しに指定されたバッファーが使用され、サイズは `setvbuf` の呼び出しで指定されたとおりにあります。  バッファー ポインターが **NULL**の場合、指定されたサイズに自動的に割り当てられるバッファーが使用されます。|  
|`_IOLBF`|`_IOFBF` と同じ。|  
|`_IONBF`|バッファーは `setvbuf`の呼び出しで引数にかかわらず、使用されません。|  
  
## 参照  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)