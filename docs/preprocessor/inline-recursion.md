---
title: "inline_recursion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "inline_recursion_CPP"
  - "vc-pragma.inline_recursion"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inline_recursion プラグマ"
  - "プラグマ, inline_recursion"
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# inline_recursion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

直接呼び出しまたは相互再帰関数の呼び出しのインライン展開を制御します。  
  
## 構文  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## 解説  
 [inline](../misc/inline-inline-forceinline.md) としてマークされている関数または [\_\_inline](../misc/inline-inline-forceinline.md) コンパイラが \/Ob2 オプションで自動的に展開する関数を制御するには、このプラグマを使用します。  このプラグマを使用するには、[\/Ob](../build/reference/ob-inline-function-expansion.md) コンパイラ オプションを 1 または 2 に設定する必要があります。  `inline_recursion` の既定の状態はオフです。  このプラグマは、以降の最初の関数呼び出しに対して効果があり、関数の定義には影響を与えません。  
  
 `inline_recursion` プラグマは再帰関数の展開方法を制御します。  `inline_recursion` が off の場合、インライン関数が自身を \(直接または間接的に\) 呼び出すと、関数は 1 回しか展開されません。  `inline_recursion` が on の場合、[inline\_depth](../preprocessor/inline-depth.md) プラグマで設定された値、`inline_depth` プラグマで定義されている再帰関数の既定値、または容量制限に達するまで、複数回展開されます。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline\_depth](../preprocessor/inline-depth.md)   
 [\/Ob \(関数のインライン展開\)](../build/reference/ob-inline-function-expansion.md)