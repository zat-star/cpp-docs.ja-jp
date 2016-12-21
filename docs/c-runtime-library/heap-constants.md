---
title: "ヒープ定数 | Microsoft Docs"
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
  - "_HEAPBADPTR"
  - "_HEAPEMPTY"
  - "_HEAPBADBEGIN"
  - "_HEAPOK"
  - "_HEAPBADNODE"
  - "_HEAPEND"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_HEAPBADBEGIN 定数"
  - "_HEAPBADNODE 定数"
  - "_HEAPBADPTR 定数"
  - "_HEAPEMPTY 定数"
  - "_HEAPEND 定数"
  - "_HEAPOK 定数"
  - "ヒープ定数"
  - "HEAPBADBEGIN 定数"
  - "HEAPBADNODE 定数"
  - "HEAPBADPTR 定数"
  - "HEAPEMPTY 定数"
  - "HEAPEND 定数"
  - "HEAPOK 定数"
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ヒープ定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <malloc.h>  
  
```  
  
## 解説  
 これらの定数は、ヒープの状態を示す戻り値が異なります。  
  
|定数|説明|  
|--------|--------|  
|`_HEAPBADBEGIN`|最初のヘッダー情報が無効見つかりません。または、ではありません。|  
|`_HEAPBADNODE`|不適切なノードが見つかりました、ヒープが傷つきます。|  
|`_HEAPBADPTR`|**\_HEAPINFO** 構造体の**\_pentry** フィールドはヒープ \(`_heapwalk` ルーチンのみ\) への有効なポインターは含まれません。|  
|`_HEAPEMPTY`|ヒープを初期化されませんでした。|  
|`_HEAPEND`|ヒープの末尾が正常に達した \(`_heapwalk` ルーチンのみ\)。|  
|`_HEAPOK`|ヒープは、一貫しています \(`_heapset` と `_heapchk` ルーチンのみ\)。  エラーがこれまで; **\_HEAPINFO** 構造体は次のエントリ \(`_heapwalk` ルーチンのみ\) に関する情報が含まれます。|  
  
## 参照  
 [\_heapchk](../c-runtime-library/reference/heapchk.md)   
 [\_heapset](../c-runtime-library/heapset.md)   
 [\_heapwalk](../Topic/_heapwalk.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)