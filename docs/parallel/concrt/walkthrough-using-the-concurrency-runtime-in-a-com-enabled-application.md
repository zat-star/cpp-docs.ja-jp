---
title: "チュートリアル: COM 対応アプリケーションでの同時実行ランタイムの使用 | Microsoft Docs"
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
  - "同時実行ランタイム、使用 (COM と)"
  - "COM、使用 (同時実行ランタイムと)"
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# チュートリアル: COM 対応アプリケーションでの同時実行ランタイムの使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このドキュメントでは、コンポーネント オブジェクト モデル \(COM\) を使用するアプリケーションで同時実行ランタイムを使用する方法について説明します。  
  
## 必須コンポーネント  
 このチュートリアルを開始する前に、次のドキュメントを参照してください。  
  
-   [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)  
  
-   [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)  
  
-   [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)  
  
 COM の詳細については、「[コンポーネント オブジェクト モデル \(COM\)](http://msdn.microsoft.com/library/windows/desktop/ms680573)」を参照してください。  
  
## COM ライブラリの有効期間の管理  
 同時実行ランタイムでの COM の使用は他の同時実行機構と同じ基本原則に従いますが、これらのライブラリを組み合わせて効率よく使用するには次のガイドラインが役に立ちます。  
  
-   スレッドでは、COM ライブラリを使用する前に [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) を呼び出す必要があります。  
  
-   スレッドでは、同じ引数を毎回提供する場合に限り、`CoInitializeEx` を複数回呼び出すことができます。  
  
-   `CoInitializeEx` の呼び出しごとに、スレッドは [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715) も呼び出す必要があります。  つまり、`CoInitializeEx` と `CoUninitialize` の呼び出しは、均等化する必要があります。  
  
-   あるスレッド アパートメントから別のアパートメントに切り替えるには、スレッドは新しいスレッド処理仕様で `CoInitializeEx` を呼び出す前に、COM ライブラリを完全に解放する必要があります。  
  
 同時実行ランタイムで COM を使用する場合は、COM に関する他の基本原則が適用されます。  たとえば、オブジェクトをシングルスレッド アパートメント \(STA: Single\-Threaded Apartment\) に作成し、そのオブジェクトを別のアパートメントにマーシャリングするアプリケーションでは、受信メッセージを処理するためのメッセージ ループも提供する必要があります。  また、アパートメント間でオブジェクトをマーシャリングすると、パフォーマンスが低下する可能性があることに注意してください。  
  
### 並列パターン ライブラリでの COM の使用  
 タスク グループや並列アルゴリズムなど、並列パターン ライブラリ \(PPL\) のコンポーネントで COM を使用するときは、各タスクまたは反復処理の間に COM ライブラリを使用する前に `CoInitializeEx` を呼び出し、各タスクまたは反復処理が終了する前に `CoUninitialize` を呼び出します。  次の例では、[concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) オブジェクトで COM ライブラリの有効期間を管理する方法を示します。  
  
 [!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]  
  
 タスクまたは並列アルゴリズムを取り消すとき、またはタスクの本体で例外をスローするときは、COM ライブラリが正しく解放されていることを確認する必要があります。  タスクが終了する前に `CoUninitialize` を確実に呼び出すには、`try-finally` ブロックまたは *Resource Acquisition Is Initialization* \(RAII\) パターンを使用します。  次の例では、`try-finally` ブロックを使用して、タスクが終了するとき、取り消されるとき、または例外がスローされるときに、COM ライブラリを解放しています。  
  
 [!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]  
  
 次の例では、RAII パターンを使用して、特定のスコープでの COM ライブラリの有効期間を管理する `CCoInitializer` クラスを定義しています。  
  
 [!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]  
  
 `CCoInitializer` クラスを使用すると、次のように、タスクが終了するときに COM ライブラリを自動的に解放できます。  
  
 [!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]  
  
 同時実行ランタイムでの取り消し処理の詳細については、「[キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)」を参照してください。  
  
### 非同期エージェントでの COM の使用  
 非同期エージェントで COM を使用するときは、エージェントの [concurrency::agent::run](../Topic/agent::run%20Method.md) メソッドで COM ライブラリを使用する前に、`CoInitializeEx` を呼び出します。  その後、`run` メソッドが返される前に `CoUninitialize` を呼び出します。  エージェントのコンストラクターまたはデストラクターでは COM 管理ルーチンを使用しないでください。また、[concurrency::agent::start](../Topic/agent::start%20Method.md) メソッドまたは [concurrency::agent::done](../Topic/agent::done%20Method.md) メソッドはオーバーライドしないでください。これらのメソッドは、`run` メソッドとは異なるスレッドから呼び出されます。  
  
 次の例では、`CCoAgent` という名前の基本的なエージェント クラスを示します。このクラスは `run` メソッドで COM ライブラリを管理します。  
  
 [!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]  
  
 詳細な例については、このチュートリアルで後ほど説明します。  
  
### 軽量タスクでの COM の使用  
 同時実行ランタイムでの軽量タスクの役割については、「[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)」を参照してください。  Windows API で `CreateThread` 関数に渡すスレッド ルーチンと同じように、軽量タスクで COM を使用できます。  これを次の例に示します。  
  
 [!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]  
  
## COM 対応のアプリケーションの例  
 このセクションでは、`IScriptControl` インターフェイスを使用して n 番目のフィボナッチ数列を計算するスクリプトを実行する、完全な COM 対応アプリケーションを示します。  この例では、最初にメイン スレッドからスクリプトを呼び出した後、PPL とエージェントを使用してスクリプトを同時に呼び出します。  
  
 次のようなヘルパー関数 `RunScriptProcedure` を使用します。この関数は、`IScriptControl` オブジェクトのプロシージャを呼び出します。  
  
 [!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]  
  
 `wmain` 関数は、`IScriptControl` オブジェクトを作成し、n 番目のフィボナッチ数列を計算するスクリプト コードをそのオブジェクトに追加した後、`RunScriptProcedure` 関数を呼び出してそのスクリプトを実行します。  
  
 [!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]  
  
### PPL からのスクリプトの呼び出し  
 次の関数 `ParallelFibonacci` は、[concurrency::parallel\_for](../Topic/parallel_for%20Function.md) アルゴリズムを使用してスクリプトを並列に呼び出します。  この関数は、`CCoInitializer` クラスを使用して、タスクの反復ごとの COM ライブラリの有効期間を管理します。  
  
 [!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]  
  
 この例で `ParallelFibonacci` 関数を使用するには、`wmain` 関数が返される前に次のコードを追加します。  
  
 [!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]  
  
### エージェントからのスクリプトの呼び出し  
 次の例では、スクリプトのプロシージャを呼び出して n 番目のフィボナッチ数列を計算する `FibonacciScriptAgent` クラスを示します。  `FibonacciScriptAgent` クラスは、メッセージ パッシングを使用して、スクリプト関数への入力値をメイン プログラムから受け取ります。  `run` メソッドは、タスク全体を通じて COM ライブラリの有効期間を管理します。  
  
 [!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]  
  
 次の `AgentFibonacci` 関数は、複数の `FibonacciScriptAgent` オブジェクトを作成し、メッセージ パッシングを使用して複数の入力値をこれらのオブジェクトに送ります。  
  
 [!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]  
  
 この例で `AgentFibonacci` 関数を使用するには、`wmain` 関数が返される前に次のコードを追加します。  
  
 [!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]  
  
### 完全な例  
 並列アルゴリズムと非同期エージェントを使用してフィボナッチ数列を計算するスクリプト プロシージャを呼び出す、完全なコード例を次に示します。  
  
 [!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
  **Main Thread:**  
**fib\(15\) \= 610**  
**Parallel Fibonacci:**  
**fib\(15\) \= 610**  
**fib\(10\) \= 55**  
**fib\(16\) \= 987**  
**fib\(18\) \= 2584**  
**fib\(11\) \= 89**  
**fib\(17\) \= 1597**  
**fib\(19\) \= 4181**  
**fib\(12\) \= 144**  
**fib\(13\) \= 233**  
**fib\(14\) \= 377**  
**Agent Fibonacci:**  
**fib\(30\) \= 832040**  
**fib\(22\) \= 17711**  
**fib\(10\) \= 55**  
**fib\(12\) \= 144**   
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`parallel-scripts.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc parallel\-scripts.cpp \/link ole32.lib**  
  
## 参照  
 [同時実行ランタイムのチュートリアル](../Topic/Concurrency%20Runtime%20Walkthroughs.md)   
 [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)   
 [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)   
 [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)   
 [キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)