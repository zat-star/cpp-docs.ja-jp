---
title: "3.2.1 omp_init_lock and omp_init_nest_lock Functions | Microsoft Docs"
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
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.1 omp_init_lock and omp_init_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらの関数はロックを初期化する唯一の方法を提供します。  各関数は後続の呼び出しでパラメーターの  *ロック*  に関連付けられているロックを初期化します。  形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 初期状態ではロックが解除されます \(つまりスレッドがロックを所有していません\)。  入れ子にできるロックでは最初の入れ子の数が返されます。  これは不適合既にロック初期化変数のこれらのルーチンのいずれかを呼び出すことができます。