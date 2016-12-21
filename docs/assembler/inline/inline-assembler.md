---
title: "インライン アセンブラー | Microsoft Docs"
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
  - "アセンブラー [C++]"
  - "アセンブラー [C++], インライン"
  - "アセンブリ言語 [C++], インライン"
  - "インライン アセンブラー [C++]"
  - "インライン アセンブラー [C++]"
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン アセンブラー
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 アセンブリ言語は、プログラムの実行速度の向上、必要メモリ量の削減、ハードウェアの制御など、さまざまな目的に適しています。  インライン アセンブラーを使用して、追加のアセンブリとリンク ステップを使用せずに、アセンブリ言語命令を C および C\+\+ のソース プログラムに直接埋め込むことができます。  インライン アセンブラーは、コンパイラに組み込まれます。したがって、MASM \(Microsoft Macro Assembler\) などの別のアセンブラーは必要ではありません。  
  
> [!NOTE]
>  インライン アセンブラー コードを含むプログラムは、他のハードウェア プラットフォームに完全に移植できるわけではありません。  移植性を考慮して設計する場合、インライン アセンブラーは使用しないでください。  
  
 インライン アセンブラーは ARM プロセッサと [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] プロセッサではサポートされていません。ここからのトピックでは、x86 プロセッサで Visual C\/C\+\+ インライン アセンブラーを使用する方法を示します。  
  
-   [インライン アセンブラーの概要](../../assembler/inline/inline-assembler-overview.md)  
  
-   [インライン アセンブラーの長所](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [\_\_asm](../../assembler/inline/asm.md)  
  
-   [\_\_asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [\_\_asm ブロックでの C または C\+\+ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [インライン アセンブリでのレジスタの使用および保持](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [インライン アセンブラーのラベルにジャンプ](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [インライン アセンブリでの C 関数の呼び出し](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [インライン アセンブリでの C\+\+ 関数の呼び出し](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [\_\_asm ブロックの C マクロとしての定義](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [インライン アセンブリの最適化](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [コンパイラの組み込みとアセンブリ言語](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [C\+\+ 言語リファレンス](../../cpp/cpp-language-reference.md)