---
title: "方法: Alloc および Free を使用してメモリ パフォーマンスを改善する | Microsoft Docs"
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
  - "Alloc と Free、使用 [同時実行ランタイム]"
  - "使用 (Alloc と Free を) [同時実行ランタイム]"
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 方法: Alloc および Free を使用してメモリ パフォーマンスを改善する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、[concurrency::Alloc](../Topic/Alloc%20Function.md) 関数および [concurrency::Free](../Topic/Free%20Function.md) 関数を使用してメモリ パフォーマンスを改善する方法について説明します。  ここでは、それぞれが `new` 演算子と `delete` 演算子を指定する、配列の 3 種類の要素を並行して反転するときの所要時間を比較します。  
  
 `Alloc` 関数と `Free` 関数は、複数のスレッドで `Alloc` と `Free` の両方を頻繁に呼び出す場合に最も役に立ちます。  ランタイムは、スレッドごとに個別のメモリ キャッシュを保持します。したがって、ランタイムは、ロックまたはメモリ バリアを使用せずにメモリを管理します。  
  
## 使用例  
 それぞれが `new` 演算子と `delete` 演算子を指定する、3 種類の例を次に示します。  `new_delete` クラスはグローバル `new` 演算子と `delete` 演算子、`malloc_free` クラスは C ランタイム [malloc](../../c-runtime-library/reference/malloc.md) 関数と [free](../../c-runtime-library/reference/free.md) 関数、`Alloc_Free` クラスは同時実行ランタイム `Alloc` 関数と `Free` 関数をそれぞれ使用します。  
  
 [!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]  
  
## 使用例  
 `swap` 関数および `reverse_array` 関数の例を次に示します。  `swap` 関数は、配列の指定されたインデックス位置の内容を交換します。  また、テンポラリ変数のヒープからメモリを割り当てます。  `reverse_array` 関数は、大きな配列を作成し、その配列を並行して複数回反転したときの所要時間を計算します。  
  
 [!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]  
  
## 使用例  
 それぞれが異なるメモリ割り当て方法を使用する `new_delete`、`malloc_free`、および `Alloc_Free` の各クラスを `reverse_array` 関数で操作したときの所要時間を計算する、`wmain` 関数の例を次に示します。  
  
 [!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]  
  
## 使用例  
 完全な例を次に示します。  
  
 [!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]  
  
 この例では、4 つのプロセッサを備えたコンピューターで次のサンプル出力を生成します。  
  
  **Took 2031 ms with new\/delete.**  
**Took 1672 ms with malloc\/free.**  
**Took 656 ms with Alloc\/Free.** この例で、`Alloc` 関数と `Free` 関数を使用する例では、`Alloc` 関数と `Free` 関数が複数スレッドのメモリ ブロックを頻繁に割り当ておよび解放する操作に対して最適化されるため、最も優れたメモリ パフォーマンスが提供されます。  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`allocators.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc allocators.cpp**  
  
## 参照  
 [メモリ管理関数](../Topic/Memory%20Management%20Functions.md)   
 [Alloc 関数](../Topic/Alloc%20Function.md)   
 [Free 関数](../Topic/Free%20Function.md)