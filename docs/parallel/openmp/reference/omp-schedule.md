---
title: "OMP_SCHEDULE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OMP_SCHEDULE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_SCHEDULE OpenMP environment variable"
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# OMP_SCHEDULE
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`schedule(runtime)` が `for` または `parallel for` のディレクティブで指定されると [schedule](../../../parallel/openmp/reference/schedule.md) 句の動作を変更します。  
  
## 構文  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## 解説  
 指定項目  
  
 `size` \(省略可能\)  
 イテレーションのサイズを指定します。  `size` は正の整数である必要があります。  既定値は `type` が静的な場合を除き1 です。  `type` が `runtime` であると無効になります。  
  
 `type`  
 スケジュールの型 :  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## 解説  
 OpenMP 標準の Visual C\+\+ の実装の既定値は `OMP_SCHEDULE=static,0` です。  
  
 詳細については、「[4.1 OMP\_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)」を参照してください。  
  
## 使用例  
 次のコマンドは **OMP\_SCHEDULE** 環境変数を設定します :  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 次のコマンドは **OMP\_SCHEDULE** 環境変数の現在の設定を示しています :  
  
```  
set OMP_SCHEDULE  
```  
  
## 参照  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)