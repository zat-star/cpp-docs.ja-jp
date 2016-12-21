---
title: "コンパイラの警告 C4746 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 C4746
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

式\>' の '\<一時的なアクセスは \/volatile:に従います。\[iso&#124;ミリ秒の設定\) ; \_\_iso\_volatile\_load\/store の組み込み関数を使用することを検討してください。  
  
 C4746 は揮発性変数が直接アクセスするたびに表示されます。  開発者が現在指定されている \([\/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) のコンパイラ オプションで制御できる\) 特定の揮発性モデルの影響を受けるコード位置を識別できるように設計されています。  特に、\/volatile:ms を使用すると、コンパイラにより生成されたハードウェアのメモリ バリアを特定するために便利です。  
  
 \_\_iso\_volatile\_load\/store の組み込みを明示的に volatile モデルに影響されない揮発性メモリにアクセスすることができます。  これらの組み込みを使用する C4746 をトリガーしない。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。