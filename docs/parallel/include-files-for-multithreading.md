---
title: "ファイルをインクルードするマルチ スレッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f71b52bca5f636d80f2d55cc5e9ffc3e217d90a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="include-files-for-multithreading"></a>マルチスレッドのためのインクルード ファイル
標準のインクルード ファイル、ライブラリで実装されていると、C ランタイム ライブラリ関数を宣言します。 使用する場合、[最大限の最適化](../build/reference/ox-full-optimization.md)(/Ox) または[fastcall 呼び出し規約](../build/reference/gd-gr-gv-gz-calling-convention.md)(/Gr) オプション、コンパイラはレジスタ呼び出し規約を使用してすべての関数を呼び出す必要があります。 ランタイム ライブラリ関数が C の呼び出し規約を使用してコンパイルされたし、標準のインクルード ファイル内の宣言がこれらの関数の適切な外部参照を生成するようにコンパイラに指示します。  
  
## <a name="see-also"></a>参照  
 [C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)