---
title: "C ランタイム エラー R6032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6032"
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# C ランタイム エラー R6032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ロケール情報のための十分な領域がありません  
  
 ランタイムは、ロケールに依存する関数呼び出しを処理できるように、各スレッドのロケールに関する情報を保持します。  この情報のメモリ割り当てに失敗した場合、ランタイムは基本的な機能の多くをその情報に依存しているため、処理を続行できなくなります。