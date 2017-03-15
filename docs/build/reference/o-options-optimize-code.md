---
title: "/O オプション (コードの最適化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.Optimization"
  - "/o"
  - "VC.Project.VCCLWCECompilerTool.Optimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, パフォーマンス"
  - "パフォーマンス, cle.exe コンパイラ"
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /O オプション (コードの最適化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/O** オプションは、実行速度を最大化またはプログラム サイズを最小化するコードの作成に役立つさまざまな最適化処理を制御します。  
  
-   [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) は、コード サイズを最小化します。  
  
-   [\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) は、実行速度を最大化します。  
  
-   [\/Ob](../../build/reference/ob-inline-function-expansion.md) は、関数のインライン展開を制御します。  
  
-   [\/Od](../../build/reference/od-disable-debug.md) は、最適化を無効にして、コンパイルの高速化およびデバッグの簡素化を実現します。  
  
-   [\/Og](../../build/reference/og-global-optimizations.md) は、グローバル最適化を有効にします。  
  
-   [\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md) は、関数呼び出し用の組み込み関数を生成します。  
  
-   [\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) は、実行速度よりもサイズの最小化のための最適化処理を優先します。  
  
-   [\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) は、サイズの最小化よりも実行速度のための最適化処理を優先します。これは既定の設定です。  
  
-   [\/Ox](../../build/reference/ox-full-optimization.md) は、最大限の最適化を選択します。  
  
-   [\/Oy](../../build/reference/oy-frame-pointer-omission.md) を指定すると、呼び出し履歴にフレーム ポインターが作成されないため、関数呼び出しが速くなります。  
  
## 解説  
 1 つのオプション ステートメントに複数の **\/O** オプションを組み合わせることもできます。  たとえば、`/Odi` は `/Od /Oi` と同じです。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)