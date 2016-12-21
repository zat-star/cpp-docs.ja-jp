---
title: "atexit の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "atexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atexit 関数"
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# atexit の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[atexit](../c-runtime-library/reference/atexit.md) 関数を使用すると、プログラムを終了する前に実行される終了処理関数を指定できます。  `atexit` を呼び出す前に初期化されたグローバルな静的オブジェクトは、終了処理関数を実行するまでは破棄されません。  
  
## 参照  
 [終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)