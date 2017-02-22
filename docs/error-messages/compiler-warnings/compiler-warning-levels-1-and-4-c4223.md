---
title: "コンパイラの警告 (レベル 1 および 4) C4223 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4223"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4223"
ms.assetid: 6fc44336-0250-4432-928b-fc5dbe7b7c1c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1 および 4) C4223
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 左辺値ではない配列をポインターに変換しました。  
  
 標準 C では、左辺値以外の配列をポインターに変換できません。  既定の Microsoft 拡張機能 \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\) では、この変換ができます。