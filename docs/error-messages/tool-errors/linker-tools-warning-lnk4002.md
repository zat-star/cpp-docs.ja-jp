---
title: "リンカー ツールの警告 LNK4002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4002"
ms.assetid: 09f81af5-e51c-496c-a6eb-2863e85375c3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# リンカー ツールの警告 LNK4002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbol は object で定義されています。  
  
 装飾された形式で表示されたシンボルは、`object` の中で装飾されていない形式で定義されていますが、装飾されたシンボルに対する一意の対応を見つけることができません。  この警告は常に警告 [LNK4022](../../error-messages/tool-errors/linker-tools-warning-lnk4022.md) の後に出力され、続いて致命的なエラー [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md) が発生します。