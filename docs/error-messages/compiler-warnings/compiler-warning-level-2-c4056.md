---
title: "コンパイラの警告 (レベル 2) C4056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4056"
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 2) C4056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点数の定数演算でオーバーフローしました。  
  
 浮動小数点定数の演算で、最大値を超える結果が生成されました。  
  
 この警告は、定数演算時に実行されたコンパイラの最適化が原因で発生する場合があります。  この警告を無視するには、最適化 \([\/Od](../../build/reference/od-disable-debug.md)\) を無効にします。  
  
 次の例では警告 C4056 が生成されます。  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```