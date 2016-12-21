---
title: "関数の型 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 関数の型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数には基本的に 2 つの型があります。  スタック フレームが必要な関数をフレーム関数といいます。  スタック フレームを必要としない関数をリーフ関数といいます。  
  
 フレーム関数は、スタック領域を割り当てたり、他の関数を呼び出したり、不揮発性レジスタを保存したり、例外処理を使用したりする関数です。  フレーム関数には、関数テーブル エントリも必要です。  フレーム関数には、プロローグとエピローグが必要です。  フレーム関数は、動的にスタック領域を割り当てて、フレーム ポインターを使用することができます。  フレーム関数を配置すると、この呼び出し標準のすべての機能を実行できます。  
  
 フレーム関数から別の関数を呼び出さない場合、スタックの整列は必要ありません \(「[スタック割り当て](../build/stack-allocation.md)」を参照\)。  
  
 リーフ関数は、関数テーブル エントリを必要としない関数です。  リーフ関数は、関数を呼び出したり、領域を割り当てたり、不揮発性レジスタを保存したりすることができません。  リーフ関数では、リーフ関数の実行時にスタックを整列しないままにすることができます。  
  
## 参照  
 [スタックの使用](../build/stack-usage.md)