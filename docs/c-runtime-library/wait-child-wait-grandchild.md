---
title: "_WAIT_CHILD、_WAIT_GRANDCHILD | Microsoft Docs"
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
  - "_WAIT_GRANDCHILD"
  - "WAIT_CHILD"
  - "WAIT_GRANDCHILD"
  - "_WAIT_CHILD"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_WAIT_CHILD 定数"
  - "_WAIT_GRANDCHILD 定数"
  - "WAIT_CHILD 定数"
  - "WAIT_GRANDCHILD 定数"
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _WAIT_CHILD、_WAIT_GRANDCHILD
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <process.h>  
  
```  
  
## 解説  
 \(プロセス ID がわかっている場合は、すべてのプロセスによって `_cwait` 関数は他のプロセスを待機するために使用できます。  操作の引数は次の値のいずれか 1 つがです:  
  
|定数|説明|  
|--------|--------|  
|`_WAIT_CHILD`|選択された新しいプロセスまでの呼び出しの待機プロセスは終了します。|  
|`_WAIT_GRANDCHILD`|選択された新しいプロセスまでの呼び出しプロセスの待機、その新しいプロセスによって作成されるすべてのプロセスは終了します。|  
  
## 参照  
 [\_cwait](../c-runtime-library/reference/cwait.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)