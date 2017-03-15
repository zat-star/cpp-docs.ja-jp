---
title: "コンパイラの警告 (レベル 3) C4723 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4723"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4723"
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 3) C4723
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

除算の 2 番目のオペランドは、コンパイル時に 0 と評価され、不定の結果を返します。  
  
 除算の 2 番目のオペランドはコンパイル時に 0 と評価され、不定の結果が返されます。  
  
 この警告が生成されるのは、[\/Og](../../build/reference/og-global-optimizations.md) オプションまたは \/Og を暗黙に指定する最適化オプションを使用している場合だけです。  
  
 この 0 オペランドは、コンパイラが生成したのものである可能性があります。