---
title: "3.1.6 omp_in_parallel Function | Microsoft Docs"
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
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.6 omp_in_parallel Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

並列実行する並列領域の動的スコープ内で呼び出された場合 **omp\_in\_parallel** の関数以外の値を返します ; それ以外の場合は 0 を返します。  形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 から呼び出されたときシリアル化する入れ子になった領域が並列実行する領域。この関数以外の値を返します。