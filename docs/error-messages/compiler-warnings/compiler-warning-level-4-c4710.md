---
title: "コンパイラの警告 (レベル 4) C4710 | Microsoft Docs"
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
  - "C4710"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4710"
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4710
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : インライン関数ではありません。  
  
 指定された関数がインライン展開の対象として選択されましたが、実際にはインライン展開されませんでした。  
  
 インライン展開はコンパイラの判断によって行われます。  **inline** キーワードは、**register** キーワードと同様にコンパイラに対する要求として使用されます。  コンパイラは、独自の判断で、特定の関数をインライン展開するかどうかを判定します。速度優先のコンパイル時は、コードの高速化が判断基準になります。サイズ優先のコンパイル時は、コードの小型化が判断基準になります。  サイズ優先のコンパイル時は、サイズが特に小さい関数だけがインライン展開されます。  
  
 機構上の理由に基づく判断により、特定の関数がインライン展開されないこともあります。  インライン展開されない場合については、「[コンパイラの警告 \(レベル 4\) C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md)」を参照してください。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。