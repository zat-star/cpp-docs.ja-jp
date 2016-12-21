---
title: "3.1.8 omp_get_dynamic Function | Microsoft Docs"
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
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.8 omp_get_dynamic Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スレッドの動的な変更が有効な場合 **omp\_get\_dynamic** 関数の戻り値は0 以外の値。それ以外の場合はを返します。  形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 実装がスレッドの数を動的に調整を実装していない場合この関数は常に 0 を返します。  
  
## cref:  
  
-   動的なスレッドの調整についてはページの 39 [セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) を参照してください。