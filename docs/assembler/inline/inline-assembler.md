---
title: "インライン アセンブラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 22f428a21af037b86e063261003baf9849357c9e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="inline-assembler"></a>インライン アセンブラー
**Microsoft 固有の仕様**  
  
 アセンブリ言語は、プログラムの実行速度の向上、必要メモリ量の削減、ハードウェアの制御など、さまざまな目的に適しています。 インライン アセンブラーを使用して、追加のアセンブリとリンク ステップを使用せずに、アセンブリ言語命令を C および C++ のソース プログラムに直接埋め込むことができます。 インライン アセンブラーは、コンパイラに組み込まれます。したがって、MASM (Microsoft Macro Assembler) などの別のアセンブラーは必要ではありません。  
  
> [!NOTE]
>  インライン アセンブラー コードを含むプログラムは、他のハードウェア プラットフォームに完全に移植できるわけではありません。 移植性を考慮して設計する場合、インライン アセンブラーは使用しないでください。  
  
 インライン アセンブラーは ARM プロセッサと [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] プロセッサではサポートされていません。  ここからのトピックでは、x86 プロセッサで Visual C/C++ インライン アセンブラーを使用する方法を示します。  
  
-   [インライン アセンブラーの概要](../../assembler/inline/inline-assembler-overview.md)  
  
-   [インライン アセンブラーの長所](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [__asm](../../assembler/inline/asm.md)  
  
-   [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [インライン アセンブリでのレジスタの使用および保持](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [インライン アセンブラーのラベルにジャンプ](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [インライン アセンブリでの C 関数の呼び出し](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [インライン アセンブリでの C++ 関数の呼び出し](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [__asm ブロックの C マクロとしての定義](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [インライン アセンブリの最適化](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込みとアセンブリ言語](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [C++ 言語リファレンス](../../cpp/cpp-language-reference.md)