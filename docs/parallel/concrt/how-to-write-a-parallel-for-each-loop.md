---
title: "方法: parallel_for_each ループを記述 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 179fa4b055b4743303f5d72ebec851a1d10def93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-write-a-parallelforeach-loop"></a>方法: parallel_for_each ループを記述する
この例を使用する方法を示しています、 [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)に含まれる素数の数を計算するアルゴリズム、 [std::array](../../standard-library/array-class-stl.md)並列オブジェクト。  
  
## <a name="example"></a>例  
 次の例では、配列に含まれる素数の数を 2 回計算します。 最初の例を使用して、 [std::for_each](../../standard-library/algorithm-functions.md#for_each)カウントを逐次的に計算するアルゴリズム。 次に、`parallel_for_each` アルゴリズムを使用して、同じタスクを並列に実行します。 また、それぞれの計算に要する時間もコンソールに出力します。  
  
 [!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]  
  
 4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。  
  
```Output  
serial version:  
found 17984 prime numbers  
took 6115 ms  
 
parallel version:  
found 17984 prime numbers  
took 1653 ms  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コードをコンパイルするコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付ける`parallel-count-primes.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc 並列-数-primes.cpp**  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 この例で `parallel_for_each` アルゴリズムに渡すラムダ式では、`InterlockedIncrement` 関数を使用して、ループの反復処理を並列で行い、カウンターを同時にインクリメントします。 `InterlockedIncrement` などの関数を使用して共有リソースへのアクセスを同期化すると、コードのパフォーマンスのボトルネックを示すことができます。 たとえばロック制御不要の同期機構を使用することができます、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)共有リソースへの同時アクセスをなくすのクラスです。 使用する例については、`combinable`この方法でクラスを参照してください[する方法: パフォーマンスを向上させる combinable を使用して](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)です。  
  
## <a name="see-also"></a>参照  
 [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_for_each 関数](reference/concurrency-namespace-functions.md#parallel_for_each)


