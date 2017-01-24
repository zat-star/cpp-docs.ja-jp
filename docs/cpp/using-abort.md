---
title: "abort の使用 | Microsoft Docs"
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
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort 関数"
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# abort の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[abort](../c-runtime-library/reference/abort.md) 関数を呼び出すと、即座に終了します。  初期化されたグローバルな静的オブジェクトの通常のデストラクション処理は実行されません。  また、`atexit` 関数を使用して指定されている特殊な処理も実行されません。  
  
## 参照  
 [終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)