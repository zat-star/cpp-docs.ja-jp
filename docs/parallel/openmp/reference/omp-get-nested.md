---
title: "omp_get_nested | Microsoft Docs"
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
  - "omp_get_nested"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_nested OpenMP function"
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_get_nested
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

入れ子になった並列化が有効かを示す値を返します。  
  
## 構文  
  
```  
int omp_get_nested( );  
```  
  
## 戻り値  
 以外の場合入れ子になった並列化が有効になります。  
  
## 解説  
 入れ子になった並列化は [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) と [OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md) に指定されます。  
  
 詳細については、「[3.1.10 omp\_get\_nested Function](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)」を参照してください。  
  
## 使用例  
 `omp_get_nested` 使用例については[omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) を参照してください。  
  
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)