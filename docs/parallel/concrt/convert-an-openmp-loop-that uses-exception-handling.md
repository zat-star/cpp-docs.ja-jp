---
title: "方法: 例外処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する | Microsoft Docs"
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
  - "例外処理、OpenMP から同時実行ランタイムへの変換"
  - "OpenMP から同時実行ランタイムへの変換、例外処理"
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: 例外処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この例では、例外処理を実行する OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../Topic/for%20\(OpenMP\).md) ループを変換して、同時実行ランタイムの例外処理機構が使用されるようにする方法を示します。  
  
 OpenMP では、並列領域でスローされた例外は、同じスレッドによって同じ領域でキャッチおよび処理される必要があります。  例外が並列領域をエスケープする場合は、ハンドルされない例外のハンドラーがそれをキャッチし、既定ではプロセスを終了します。  
  
 同時実行ランタイムでは、タスク グループ \([concurrency::task\_group](../Topic/task_group%20Class.md) オブジェクトや [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) オブジェクトなど\)、または並列アルゴリズム \(例: [concurrency::parallel\_for](../Topic/parallel_for%20Function.md)\) に渡す処理関数の本体で例外をスローすると、ランタイムはその例外を保存し、タスク グループまたはアルゴリズムが終了するまで待機しているコンテキストにその例外をマーシャリングします。  タスク グループの場合、待機しているコンテキストは、[concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md)、[concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md)、[concurrency::task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md)、または [concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md) を呼び出すコンテキストです。  並列アルゴリズムの場合、待機しているコンテキストは、そのアルゴリズムを呼び出したコンテキストです。  また、ランタイムは、タスク グループ内のすべてのアクティブ タスク \(子タスク グループ内のタスクも含む\) を中断すると共に、開始されていないすべてのタスクを破棄します。  
  
## 使用例  
 この例では、OpenMP `parallel` 領域および `parallel_for` の呼び出しで例外を処理する方法を示します。  `do_work` 関数は、失敗して [std::bad\_alloc](../../standard-library/bad-alloc-class.md) 型の例外をスローするメモリ割り当て要求を実行します。  OpenMP を使用するバージョンでは、例外をスローするスレッドは例外のキャッチも行う必要があります。  つまり、OpenMP 並列ループの各反復で例外が処理される必要があります。  同時実行ランタイムを使用するバージョンでは、メイン スレッドは別のスレッドによってスローされる例外をキャッチします。  
  
 [!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/CPP/convert-an-openmp-loop-that uses-exception-handling_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **Using OpenMP...**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**Using the Concurrency Runtime...**  
**An error of type 'class std::bad\_alloc' occurred.** この例に示す OpenMP を使用するバージョンでは、各ループ反復で例外が発生し、処理されます。  同時実行ランタイムを使用するバージョンでは、ランタイムが例外を保存し、すべてのアクティブ タスクを停止すると共に、まだ開始されていないタスクを破棄し、`parallel_for` を呼び出すコンテキストに例外をマーシャリングします。  
  
 OpenMP を使用するバージョンを例外発生後に終了する必要がある場合は、ブール型のフラグを使用して、エラーが発生したことを他のループ反復に通知します。  「[方法: キャンセル処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)」の例に示すとおり、フラグが設定されている場合、それ以降のループ反復では何も行われません。  一方、同時実行ランタイムを使用するループを例外発生後に続行する必要がある場合は、並列ループの本体で例外を処理します。  
  
 非同期エージェントや軽量タスクなど、同時実行ランタイムの他のコンポーネントでは、例外は転送されません。  代わりに、ハンドルされない例外のハンドラーが例外をキャッチし、既定ではプロセスを終了します。  例外処理の詳細については、「[例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)」を参照してください。  
  
 `parallel_for` および他の並列アルゴリズムの詳細については、「[並列アルゴリズム](../Topic/Parallel%20Algorithms.md)」を参照してください。  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`concrt-omp-exceptions.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-exceptions.cpp**  
  
## 参照  
 [OpenMP から同時実行ランタイムへの移行](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)   
 [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)