---
title: "-O オプション (コードの最適化) |Microsoft ドキュメント"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
dev_langs:
- C++
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7da04384d0c4ea00c2eaaedbcf0ec770e216289
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="o-options-optimize-code"></a>/O オプション (コードの最適化)

**/O**さまざまなオプションを制御するための最適化が最高速度または最小サイズのコードを作成します。

- [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)最小サイズのコードを生成するための最適化の組み合わせを設定します。

- [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)最高速度でコードを最適化する最適化の組み合わせを設定します。

- [/Ob](../../build/reference/ob-inline-function-expansion.md)関数のインライン展開を制御します。

- [/Od](../../build/reference/od-disable-debug.md)を高速化するコンパイルおよびデバッグを簡略化の最適化を無効にします。

- [/Og](../../build/reference/og-global-optimizations.md)グローバルな最適化を有効にします。

- [/Oi](../../build/reference/oi-generate-intrinsic-functions.md)適切な関数の呼び出しのための組み込み関数を生成します。

- [/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)コンパイラが最適化の方法をサイズの最適化を最優先に指示します。

- [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) (既定の設定) のサイズの最適化で速度の最適化を優先するようにコンパイラに指示します。

- [/Ox](../../build/reference/ox-full-optimization.md)速度に重点を置いて、最適化のいくつかを選択する組み合わせオプションです。 厳密なサブセットでは、 **/O2**最適化します。

- [/Oy](../../build/reference/oy-frame-pointer-omission.md)方が手軽な関数の呼び出しの呼び出し履歴にフレーム ポインターの作成を抑制します。

## <a name="remarks"></a>コメント

複数を組み合わせることができます**/O**オプションを 1 つのオプションのステートメントにします。 たとえば、 **/Odi**と同じ**/Od/Oi**です。 特定のオプションは相互に排他的で一緒に使用する場合、コンパイラ エラーが発生します。 個々 の**/O**詳細については、オプションです。

## <a name="see-also"></a>参照

[コンパイラ オプション](../../build/reference/compiler-options.md)   
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)