---
title: "致命的なエラー C1126 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1126"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1126"
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 致命的なエラー C1126
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 自動割り当てが size を超えました。  
  
 関数のローカル変数に割り当てられた空間およびコンパイラによって使用される空間 \(スワップ可能な関数に必要な 20 バイト\) が、制限を超えています。  
  
 このエラーを修正するには、`malloc` または `new` を使用して、大容量のデータを割り当てます。