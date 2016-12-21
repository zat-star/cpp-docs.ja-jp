---
title: "インライン アセンブリの最適化 | Microsoft Docs"
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
helpviewer_keywords: 
  - "__asm キーワード [C++], 最適化"
  - "インライン アセンブラー, 最適化"
  - "最適化, インライン アセンブラー"
  - "最適化 (パフォーマンスの), インライン アセンブラー"
  - "ストレージ, インライン アセンブリの最適化"
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン アセンブリの最適化
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 関数の `__asm` ブロックが存在すると複数の方法で最適化に影響します。  最初にコンパイラは `__asm` ブロック自体を最適化しません。  アセンブリ言語で記述した内容を正確に取得のようになります。  第 2 に`__asm` ブロックの影響のレジスタ変数の格納が存在する。  コンパイラはレジスタの内容が変更された場合 `__asm` ブロック `__asm` ブロックを渡す変数を使うと呼ばれます  最後に他のある関数全体の最適化は関数のアセンブリ言語の方法に影響されます。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)