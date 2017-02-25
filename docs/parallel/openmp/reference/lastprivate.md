---
title: "lastprivate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "lastprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lastprivate OpenMP clause"
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# lastprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

どのスレッドが最後のイテレーション \(の場合\) またはループ構造の最後のセクション \(\#pragma セクション\) を実装する外側のコンテキストでは変数のバージョンがプライベート バージョンと等しい値に設定であることを指定します。  
  
## 構文  
  
```  
lastprivate(var)  
```  
  
## 解説  
 指定項目  
  
 `var`  
 どのスレッドが最後のイテレーション \(の場合\) またはループ構造の最後のセクション \(\#pragma セクション\) を実装するセットのバージョンがプライベートである変数。  
  
## 解説  
 `lastprivate` は次のディレクティブに対象 :  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、「[2.7.2.3 lastprivate](../Topic/2.7.2.3%20lastprivate.md)」を参照してください。  
  
## 使用例  
 `lastprivate` 句の使用例については[schedule](../../../parallel/openmp/reference/schedule.md) を参照してください。  
  
## 参照  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)