---
title: "コンパイラの警告 (レベル 4) C4611 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4611"
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' と C\+\+ オブジェクト デストラクション間での相互作用には互換性がありません。  
  
 一部のプラットフォームでは、**catch** を含んだ関数は、スコープ範囲外のときは C\+\+ オブジェクトのデストラクター形式をサポートしない可能性があります。  
  
 予測できない動作を回避するため、コンストラクターおよびデストラクターを持つ関数では **catch** を使用しないでください。  
  
 この警告が 1 回だけ生成される場合は、「[warning](../../preprocessor/warning.md)」を参照してください。