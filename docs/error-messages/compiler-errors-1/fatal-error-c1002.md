---
title: "致命的なエラー C1002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1002"
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 致命的なエラー C1002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パス 2 の実行中に、ヒープ領域を使い果たしました。  
  
 コンパイラのパス 2 の実行中に、動的メモリ空間を使い果たしました。プログラムのシンボルの数が多すぎるか、または式が複雑すぎるためと考えられます。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  ソース ファイルを複数の小さいサイズのファイルに分割します。  
  
2.  式を小さな部分式に分割します。  
  
3.  メモリを消費するほかのプログラムやドライバーを削除します。