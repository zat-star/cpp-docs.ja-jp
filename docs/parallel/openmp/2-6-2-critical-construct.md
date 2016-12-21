---
title: "2.6.2 critical Construct | Microsoft Docs"
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
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.2 critical Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**重大**  のディレクティブはシングル スレッドに関連付けられた構造化ブロックの実行を一度に制限する構造体を指定します。   **重大**  のディレクティブの構文は次のとおりです :  
  
```  
#pragma omp critical [(name)]  new-line  
   structured-block  
```  
  
 オプションの  *名前が*  重要な部分を識別するために使用されることがあります。  クリティカル領域を識別するために使用する識別子には外部リンケージが表示されラベルタグメンバーおよび通常の識別子で使用される名前空間とは別の名前空間にあります。  
  
 スレッドはクリティカル領域の先頭に他のスレッドが同じ名前を持つクリティカル領域 \(任意のプログラムでは\) を実装しないまで待機します。  同じ未指定の名前へのすべての名前  **重大**  ディレクティブのマップ。