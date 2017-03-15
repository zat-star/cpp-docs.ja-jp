---
title: "omp_get_dynamic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_get_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_dynamic OpenMP function"
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# omp_get_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

後続の並列領域で使用できるスレッドの数が実行時までに調整できる示す値を返します。  
  
## 構文  
  
```  
int omp_get_dynamic();  
```  
  
## 戻り値  
 以外の場合スレッドの動的な場合は有効になります。  
  
## 解説  
 スレッドの調整は動的に[omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)指定[OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)されます。  
  
 詳細については、「[3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)」を参照してください。  
  
## 使用例  
 `omp_get_dynamic` 使用例については[omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) を参照してください。  
  
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)