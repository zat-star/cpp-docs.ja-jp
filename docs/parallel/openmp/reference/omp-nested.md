---
title: "OMP_NESTED | Microsoft Docs"
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
  - "OMP_NESTED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_NESTED OpenMP environment variable"
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_NESTED
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

入れ子になった並列化が `omp_set_nested` を有効にするか無効か入れ子になった並列化が有効かどうかを指定します。  
  
## 構文  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## 解説  
 `OMP_NESTED` 環境変数を [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) の関数によってオーバーライドできます。  
  
 OpenMP 標準の Visual C\+\+ の実装の既定値は `OMP_DYNAMIC=FALSE` です。  
  
 詳細については、「[4.4 OMP\_NESTED](../Topic/4.4%20OMP_NESTED.md)」を参照してください。  
  
## 使用例  
 次のコマンドは true に `OMP_NESTED` 環境変数を設定します :  
  
```  
set OMP_NESTED=TRUE  
```  
  
 次のコマンドは `OMP_NESTED` 環境変数の現在の設定を示しています :  
  
```  
set OMP_NESTED  
```  
  
## 参照  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)