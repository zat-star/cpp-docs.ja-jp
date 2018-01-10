---
title: "-Q オプション (低水準の操作) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /q
dev_langs: C++
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.assetid: 9fa738b9-630a-4bde-bc87-bdfa30552be4
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d970c2de5e34840ab2ed77f229c329db3c6f72fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="q-options-low-level-operations"></a>/Q オプション (低水準の操作)
使用することができます、 **/Q**次の低水準のコンパイラ操作を行うためにコンパイラ オプション。  
  
-   [/Qfast_transcendentals (超越関数高速)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): 高速超越関数を生成します。  
  
-   [/Qifist (_ftol を抑制する呼び出しません)](../../build/reference/qifist-suppress-ftol.md): 抑制`_ftol`浮動小数点型から整数型への変換が必要な (x86 のみ) の場合。  
  
-   [/Qimprecise_fwaits (Try ブロック内部の fwaits の削除)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): 削除`fwait`内コマンド`try`ブロックします。  
  
-   [/Qpar (自動並行化)](../../build/reference/qpar-auto-parallelizer.md): とマークされているループの自動並列化を有効、 [#pragma loop()](../../preprocessor/loop.md)ディレクティブです。  
  
-   [/Qpar-report (自動並行化レポート作成レベル)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): 自動並列化のレベルのレポートを有効にします。  
  
-   [/Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): 浮動小数点レジスタの読み込みし、メモリと MMX 間を移動登録用に最適化を抑制します。  
  
-   [/Qvec-report (自動ベクター化レポート作成レベル)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): 自動ベクター化のレベルのレポートを有効にします。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)