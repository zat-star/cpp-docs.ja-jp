---
title: "2.6.1 master Construct | Microsoft Docs"
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
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.1 master Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**マスター**  のディレクティブはチームのマスター スレッドによって実行される構造化ブロックを指定する構造体を指定します。   **マスター**  のディレクティブの構文は次のとおりです :  
  
```  
#pragma omp master new-line  
   structured-block  
```  
  
 チームの他のスレッドは構造化のブロックを実行しません。  エントリへまたはマスターの構造から終了に暗黙的なバリアはありません。