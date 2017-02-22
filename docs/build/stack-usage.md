---
title: "スタックの使用 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# スタックの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RSP の現在のアドレスを超えるメモリはすべて揮発性と見なされます。ユーザー デバッグ セッションまたは割り込みハンドラー中に、OS またはデバッガーがこのメモリを上書きすることがあります。  したがって、常に、スタック フレームに対して値の読み込みまたは書き込みを行う前に RSP を設定しておく必要があります。  
  
 このセクションでは、ローカル変数のためのスタック領域の割り当てと、**alloca** 組み込み関数について説明します。  
  
-   [スタック割り当て](../build/stack-allocation.md)  
  
-   [動的なパラメーター スタック領域の構成](../Topic/Dynamic%20Parameter%20Stack%20Area%20Construction.md)  
  
-   [関数の型](../build/function-types.md)  
  
-   [malloc アライメント](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## 参照  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)