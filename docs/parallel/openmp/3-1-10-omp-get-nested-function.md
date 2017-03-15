---
title: "3.1.10 omp_get_nested Function | Microsoft Docs"
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
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.10 omp_get_nested Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

無効になっている場合入れ子になった並列化を有効にすると0 `omp_get_nested` の関数以外の値を返します。  入れ子になった並列化の詳細についてはページの 40 3.1.9 セクションを参照してください。  形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 実装は入れ子になった並列化を実行する場合は常に 0 を返します。