---
title: "inline_depth | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "inline_depth_CPP"
  - "vc-pragma.inline_depth"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inline_depth プラグマ"
  - "プラグマ, inline_depth"
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# inline_depth
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\(呼び出し先で\) `n` を超える深度になる場合に関数がインライン展開されないようにインライン ヒューリスティック検索の深さを指定します。  
  
## 構文  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## 解説  
 このプラグマは、[inline](../misc/inline-inline-forceinline.md) または [\_\_inline](../misc/inline-inline-forceinline.md) を指定された関数と、\/Ob2 オプションで自動的にインライン化された関数のインライン展開を制御します。  
  
 `n` は 0 ～ 255 の値になります。255 は呼び出し先の深さが無制限であることを意味し、0 はインライン展開を禁じます。  `n` が指定されていない場合、既定値 \(254\) が使用されます。  
  
 **inline\_depth** プラグマは一連の関数呼び出しを展開できる回数を制御します。  たとえば、インライン展開の深さが 4 の場合、A が B を呼び出してから、B が C を呼び出すと、3 回の呼び出しはすべてインライン展開されます。  ただし、最も近いインライン展開が 2 の場合は、A と B のみ展開され、C は関数呼び出しとして残ります。  
  
 このプラグマを使用するには、\/Ob コンパイラ オプションを 1 または 2 に設定する必要があります。  このプラグマを使用して設定した深さは、プラグマの後の最初の関数呼び出し時に有効になります。  
  
 インライン展開の深さは展開時に減らすことができますが、増やすことはできません。  インライン展開の深さが 6 で、展開時にプリプロセッサで値が 8 の **inline\_depth** プラグマが検出された場合、深さは 6 のままです。  
  
 **inline\_depth** プラグマは、`__forceinline` でマークされた関数には影響しません。  
  
> [!NOTE]
>  再帰関数は、最大深度である 16 回の呼び出しまでインラインで置き換えることができます。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline\_recursion](../preprocessor/inline-recursion.md)