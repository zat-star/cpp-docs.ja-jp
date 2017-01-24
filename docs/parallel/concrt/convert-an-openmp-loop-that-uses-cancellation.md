---
title: "方法: キャンセル処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する | Microsoft Docs"
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
  - "変換 (OpenMP から同時実行ランタイムに)、キャンセル"
  - "キャンセル、変換 (OpenMP から同時実行ランタイムに)"
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: キャンセル処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

並列ループによっては、すべての反復を必ずしも実行する必要はありません。  たとえば、値を検索するアルゴリズムは、値が見つかれば終了できます。  OpenMP には、並列ループを抜けるための機構は用意されていません。  ただし、ブール値 \(フラグ\) を使用して、ループの反復処理時に、解決策が見つかったことを通知できます。  同時実行ランタイムの場合、先行のタスクによって、まだ開始されていない他のタスクを取り消すことができます。  
  
 この例では、必ずしもすべての反復を実行する必要のない OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../Topic/for%20\(OpenMP\).md) ループを変換して、同時実行ランタイムの取り消し機構が使用されるようにする方法を示します。  
  
## 使用例  
 この例では、OpenMP と同時実行ランタイムの両方を使用して、[std::any\_of](../Topic/any_of.md) アルゴリズムの並列バージョンを実装しています。  この例に示す OpenMP バージョンでは、フラグを使用して、条件が満たされたときにすべての並列ループ反復で調整が行われるようにしています。  同時実行ランタイムを使用するバージョンでは、[concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md) メソッドを使用して、条件が満たされたときに操作全体が停止されるようにしています。  
  
 [!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/CPP/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **Using OpenMP...**  
**9114046 is in the array.**  
**Using the Concurrency Runtime...**  
**9114046 is in the array.** OpenMP を使用するバージョンでは、フラグが設定されている場合でも、すべてのループ反復が実行されます。  さらに、タスクに子タスクが含まれている場合は、それらの子タスクにもフラグによって取り消しが通知される必要があります。  同時実行ランタイムでは、タスク グループが取り消されると、ランタイムは子タスクを含む全処理ツリーを取り消します。  [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) アルゴリズムでは、いくつかのタスクを使用して処理を実行します。  そのため、ループの 1 つの反復でルート タスクが取り消されると、計算ツリー全体が取り消されます。  処理ツリーが取り消された場合、ランタイムは新しいタスクを開始しません。  ただし、既に開始されているタスクは終了できます。  したがって、`parallel_for_each` アルゴリズムの場合、アクティブなループ反復によってリソースがクリーンアップされることがあります。  
  
 この例に示すどちらのバージョンでも、配列に検索対象値の複数のコピーが含まれている場合は、複数のループ反復でそれぞれ同時に結果が設定され、操作全体が取り消されることがあります。  条件が満たされたときに 1 つのタスクだけが実行されるようにする必要がある場合は、クリティカル セクションなどの同期プリミティブを使用できます。  
  
 また、例外処理を使用して、PPL を使用するタスクを取り消すこともできます。  キャンセル処理の詳細については、「[キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)」を参照してください。  
  
 `parallel_for_each` および他の並列アルゴリズムの詳細については、「[並列アルゴリズム](../Topic/Parallel%20Algorithms.md)」を参照してください。  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`concrt-omp-parallel-any-of.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-parallel\-any\-of.cpp**  
  
## 参照  
 [OpenMP から同時実行ランタイムへの移行](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)