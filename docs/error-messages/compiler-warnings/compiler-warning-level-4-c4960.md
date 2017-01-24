---
title: "コンパイラの警告 (レベル 4) C4960 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4960"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4960"
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4960
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' はプロファイルするには多き過ぎます  
  
 [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) を使用するときに、命令が 65,535 を超える関数を含む入力モジュールが検出されました。 このような大きい関数は、ガイド付き最適化のプロファイルに使用できません。  
  
 この警告を解決するには、関数のサイズを小さくします。