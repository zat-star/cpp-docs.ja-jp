---
title: "2.6.6 ordered Construct | Microsoft Docs"
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
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.6 ordered Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**順序あり**  のディレクティブの後ろに構造化ブロックは順次ループの反復処理が実行される順序で実行されます。   **順序あり**  のディレクティブの構文は次のとおりです :  
  
```  
#pragma omp ordered new-line  
   structured-block  
```  
  
 **順序あり**  のディレクティブは **For** または構造体の動的  **並列の**  の範囲内である必要があります。   **順序あり**  の構造をバインドする **For** または  **並列の**  のディレクティブはページで [セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 11. に従って指定された  **順序あり**  の句が必要です。   **順序あり**  の句を使用して **For** または  **並列の**  構造の実行では **順序あり**  の構造はループの順次実行で実行される順序でのみ実行されます。  
  
 **順序あり**  のディレクティブに制限 : は次のとおりです。  
  
-   **For** の構造体を含むループの反復処理が同じ順序ありのディレクティブを複数回実行することは  **順序あり**  の複数のディレクティブを実行する必要はありません。