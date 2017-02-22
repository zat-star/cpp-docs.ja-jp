---
title: "/Q オプション (低水準の操作) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/q"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Q コンパイラ オプション [C++]"
  - "-Q コンパイラ オプション [C++]"
  - "/Q コンパイラ オプション [C++]"
ms.assetid: 9fa738b9-630a-4bde-bc87-bdfa30552be4
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# /Q オプション (低水準の操作)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Q** コンパイラ オプションを使用して、次に示す低水準のコンパイラ操作を実行できます。  
  
-   [\/Qfast\_transcendentals \(超越関数高速化の強制\)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): 高速化した超越関数を生成します。  
  
-   [\/QIfist \(\_ftol を呼び出さない\)](../../build/reference/qifist-suppress-ftol.md): 浮動小数点型から整数型への変換が必要なときに、`_ftol` を呼び出しません \(x86 のみ\)。  
  
-   [\/Qimprecise\_fwaits \(try ブロック内部の fwaits を削除する\)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): `try` ブロックの中にある `fwait` コマンドを削除します。  
  
-   [\/Qpar \(自動並行化\)](../Topic/-Qpar%20\(Auto-Parallelizer\).md): [\#pragma loop\(\)](../../preprocessor/loop.md) ディレクティブでマークされているループの自動並列化を有効にします。  
  
-   [\/Qpar\-report \(自動並行化レポート作成レベル\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): 自動並列化のレポート レベルを有効にします。  
  
-   [\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md): 浮動小数点レジスタの読み込み用、およびメモリと MMX レジスタとの間の移動用に最適化しません。  
  
-   [\/Qvec\-report \(自動ベクター化レポート作成レベル\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): 自動ベクター化のレポート レベルを有効にします。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)