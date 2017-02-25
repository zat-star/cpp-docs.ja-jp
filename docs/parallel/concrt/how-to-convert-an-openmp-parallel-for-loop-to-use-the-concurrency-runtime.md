---
title: "方法: OpenMP の parallel for ループを変換し、同時実行ランタイムを使用する | Microsoft Docs"
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
  - "変換 (OpenMP から同時実行ランタイムに)、parallel for ループ"
  - "変換 (OpenMP から同時実行ランタイムに)、並列ループ"
  - "parallel for ループ、変換 (OpenMP から同時実行ランタイムに)"
  - "並列ループ、変換 (OpenMP から同時実行ランタイムに)"
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 方法: OpenMP の parallel for ループを変換し、同時実行ランタイムを使用する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この例では、OpenMP の [parallel](../../parallel/openmp/reference/parallel.md) ディレクティブと [for](../Topic/for%20\(OpenMP\).md) ディレクティブを使用する基本的なループを取り上げ、同時実行ランタイムの [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) アルゴリズムを使用するように切り替える方法について説明します。  
  
## 使用例  
 この例では、OpenMP と同時実行ランタイムの両方を使用して、ランダム値の配列に含まれる素数の数を計算します。  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/CPP/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **Using OpenMP...**  
**found 107254 prime numbers.**  
**Using the Concurrency Runtime...**  
**found 107254 prime numbers.** `parallel_for` アルゴリズムおよび OpenMP 3.0 では、インデックス型を符号付き整数型として使用することも、符号なし整数型として使用することもできます。  また、`parallel_for` アルゴリズムを使用すると、指定の範囲が符号付きの型をオーバーフローすることがなくなります。  OpenMP Version 2.0 および 2.5 では、符号付き整数のインデックス型しか使用できません。  また、OpenMP でインデックス範囲は検証されません。  
  
 この例の同時実行ランタイムを使用するバージョンでは、[atomic](../../parallel/openmp/reference/atomic.md) ディレクティブの代わりに [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) オブジェクトを使用して、同期処理なしでカウンター値をインクリメントします。  
  
 `parallel_for` および他の並列アルゴリズムの詳細については、「[並列アルゴリズム](../Topic/Parallel%20Algorithms.md)」を参照してください。  `combinable` クラスの詳細については、「[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。  
  
## 使用例  
 この例では、前の例を変更して、ネイティブ配列に対してではなく、[std::array](../../standard-library/array-class-stl.md) オブジェクトに対して作用するようにしています。  OpenMP Version 2.0 および 2.5 では、`parallel` `for` コンストラクトで符号付き整数のインデックス型しか許容されないため、反復子を使用して標準テンプレート ライブラリ \(STL\) コンテナーの要素に並列にアクセスすることはできません。  並列パターン ライブラリ \(PPL\) では、[concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) アルゴリズムを使用して、反復コンテナー \(STL によって提供された反復コンテナーなど\) に対してタスクを並列に実行できます。  このアルゴリズムでは、`parallel_for` アルゴリズムで使用されるのと同じ分割ロジックが使用されます。  `parallel_for_each` アルゴリズムは STL [std::for\_each](../Topic/for_each.md) アルゴリズムと似ていますが、`parallel_for_each` アルゴリズムではタスクが同時に実行される点が異なります。  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/CPP/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`concrt-omp-count-primes.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-count\-primes.cpp**  
  
## 参照  
 [OpenMP から同時実行ランタイムへの移行](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)   
 [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)