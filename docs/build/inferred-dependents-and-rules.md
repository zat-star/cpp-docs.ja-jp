---
title: "推論による依存ファイルと推論規則 | Microsoft Docs"
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
helpviewer_keywords: 
  - "依存, 推論による"
  - "推論による依存ファイル (NMAKE の)"
  - "推論規則 (NMAKE の)"
  - "規則, 推論による"
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 推論による依存ファイルと推論規則
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

適切な推論規則が存在する場合、NMAKE は、ターゲットに対応する依存ファイルとして、推論による依存ファイルを想定します。  規則は、次の場合に適用されます。  
  
-   *toext* がターゲットの拡張子と一致する。  
  
-   現在のディレクトリまたは指定されたディレクトリに存在し、ターゲットと同じベース名を持つファイルの拡張子と *fromext* が一致する。  
  
-   *fromext* が [.SUFFIXES](../build/dot-directives.md) に存在し、一致規則のほかの *fromext* よりも **.SUFFIXES** 優先順位が高い。  
  
-   **.SUFFIXES** 優先順位で上回る明示的な依存ファイルが存在しない。  
  
 推論による依存ファイルによって、予測不可能な副作用が発生することがあります。  ターゲットの記述ブロックにコマンドがある場合、NMAKE は規則のコマンドの代わりにそれらのコマンドを実行します。  
  
## 参照  
 [推論規則](../build/inference-rules.md)