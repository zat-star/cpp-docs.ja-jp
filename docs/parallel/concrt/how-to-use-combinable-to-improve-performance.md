---
title: "方法: combinable を使用してパフォーマンスを向上させる | Microsoft Docs"
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
  - "combinable クラス、例"
  - "向上 (combinable を使用して並行処理のパフォーマンスを) [同時実行ランタイム]"
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 方法: combinable を使用してパフォーマンスを向上させる
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この例では、[concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) クラスを使用して、[std::array](../../standard-library/array-class-stl.md) オブジェクト内の素数の合計を計算する方法について説明します。  `combinable` クラスは、共有状態を解消することでパフォーマンスを向上します。  
  
> [!TIP]
>  場合によっては、並行してマップ \([concurrency::parallel\_transform](../Topic/parallel_transform%20Function.md)\) および縮小 \([concurrency:: parallel\_reduce](../Topic/parallel_reduce%20Function.md)\) を実行する方が `combinable` よりもパフォーマンスがよい場合があります。  この例と同じ結果を生成するためにマップ操作と縮小操作を使用する例については、「[並列アルゴリズム](../Topic/Parallel%20Algorithms.md)」を参照してください。  
  
## 使用例  
 次の例では、[std::accumulate](../Topic/accumulate.md) 関数を使用して、配列に含まれる素数の要素の合計を計算します。  この例では、`a` は `array` オブジェクトであり、入力値が素数であるかどうかを判定するために `is_prime` 関数を使用します。  
  
 [!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_1.cpp)]  
  
## 使用例  
 次の例では、前の例の並列化を単純な方法で示します。  この例では、[concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) アルゴリズムを使用して配列を並列で処理し、[concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) オブジェクトを使用して `prime_sum` 変数へのアクセスを同期します。  この例では、共有リソースが使用できるようになるのを各スレッドが待機する必要があるため、効率は改善されません。  
  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_2.cpp)]  
  
## 使用例  
 `combinable` オブジェクトを使用して、前の例のパフォーマンスを向上する例を次に示します。  この例では、同期オブジェクトが不要となっています。`combinable` オブジェクトを使用することにより、各スレッドがタスクを独立して実行できるため、効率が改善されます。  
  
 通常、`combinable` オブジェクトは次の手順で使用します。  最初に、処理を並列で実行して、詳細な計算結果を生成します。  次に、この計算結果を結合 \(換算\) して最終結果を生成します。  この例では、[concurrency::combinable::local](../Topic/combinable::local%20Method.md) メソッドを使用して、ローカルの合計への参照を取得します。  次に、[concurrency::combinable::combine](../Topic/combinable::combine%20Method.md) メソッドおよび [std::plus](../../standard-library/plus-struct.md) オブジェクトを使用して、ローカルの計算を結合して最終結果を得ます。  
  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_3.cpp)]  
  
## 使用例  
 次のコード例全体では、素数の合計を逐次処理と並列処理の両方で計算します。  この例では、両方の計算に要する時間もコンソールに出力します。  
  
 [!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_4.cpp)]  
  
 4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。  
  
  **1709600813**  
**逐次時: 6178 ミリ秒**  
**1709600813**  
**並列時: 1638 ミリ秒**   
## コードのコンパイル  
 このコードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、`parallel-sum-of-primes.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc parallel\-sum\-of\-primes.cpp**  
  
## 信頼性の高いプログラミング  
 同じ結果を生成するためにマップ操作と縮小操作を使用する例については、「[並列アルゴリズム](../Topic/Parallel%20Algorithms.md)」を参照してください。  
  
## 参照  
 [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable クラス](../../parallel/concrt/reference/combinable-class.md)   
 [critical\_section クラス](../../parallel/concrt/reference/critical-section-class.md)