---
title: "3.3 Timing Routines | Microsoft Docs"
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
ms.assetid: 21060d64-cbe8-4e38-8718-3a68d6a57be3
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.3 Timing Routines
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このセクションで説明する関数は汎用性ウォール クロック時間をサポートします :  
  
-   `omp_get_wtime` 関数の戻り値はウォール クロック時間の経過します。  
  
-   連続するクロックのサウンド間の `omp_get_wtick` 関数の戻り値の秒。