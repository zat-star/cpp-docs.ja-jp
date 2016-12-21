---
title: "方向フラグ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "方向フラグ"
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 方向フラグ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

方向フラグは 80x86 Intel プロセッサに CPU フラグの仕様です。  これは、移動、MOVSD、MOVSW などの REP \(繰り返し\) プリフィックスを使用するすべてのアセンブリ命令に適用されます。  アドレスは、適度な手順に方向フラグがオフの増加が用意されていました。  
  
 C のランタイム ルーチンは方向フラグがオフになっていることを前提としています。  C のランタイム関数から他の関数を使用すると、他の関数が方向フラグをそのまま、または元の状態に復元する必要があります。  方向フラグが要求すると、エントリに明確であるとランタイム コードをより高速かつ効率的になります。  
  
 C ランタイム ライブラリ関数は、文字列操作およびバッファー ルーチン操作などをオフにすると、方向フラグが必要になります。  
  
## 参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)