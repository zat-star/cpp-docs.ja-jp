---
title: "OMP_DYNAMIC | Microsoft Docs"
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
  - "OMP_DYNAMIC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_DYNAMIC OpenMP environment variable"
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP の実行時の並列領域のスレッド数を調整できるかどうかを指定します。  
  
## 構文  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## 解説  
 `OMP_DYNAMIC` 環境変数を [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) の関数によってオーバーライドできます。  
  
 OpenMP 標準の Visual C\+\+ の実装の既定値は `OMP_DYNAMIC=FALSE` です。  
  
 詳細については、「[4.3 OMP\_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)」を参照してください。  
  
## 使用例  
 次のコマンドは true に `OMP_DYNAMIC` 環境変数を設定します :  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 次のコマンドは `OMP_DYNAMIC` 環境変数の現在の設定を示しています :  
  
```  
set OMP_DYNAMIC  
```  
  
## 参照  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)