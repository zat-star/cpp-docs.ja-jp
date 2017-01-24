---
title: "方法: 並列呼び出しを使用して並列並べ替えルーチンを記述する | Microsoft Docs"
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
  - "task_handle クラス、例"
  - "task_group クラス、例"
  - "make_task 関数、例"
  - "structured_task_group クラス、例"
  - "向上 (タスク グループを使用して並行処理のパフォーマンスを) [同時実行ランタイム]"
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
caps.latest.revision: 23
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: 並列呼び出しを使用して並列並べ替えルーチンを記述する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、[parallel\_invoke](../Topic/parallel_invoke%20Function.md) アルゴリズムを使用して、バイトニック ソート アルゴリズムのパフォーマンスを向上させる方法について説明します。  バイトニック ソート アルゴリズムでは、入力シーケンスを、より小さな並べ替え済みのパーティションへと再帰的に分割します。  各パーティションの操作は他のすべての操作から独立しているため、バイトニック ソート アルゴリズムは並列的に実行することができます。  
  
 バイトニック ソートは、入力シーケンスのあらゆる組み合わせを並べ替える*ソーティング ネットワーク*の 1 つではありますが、この例で並べ替えるのは、長さが 2 の累乗であるシーケンスです。  
  
> [!NOTE]
>  この例では、例を示す目的で、並列並べ替えルーチンを使用します。  また、[concurrency::parallel\_sort](../Topic/parallel_sort%20Function.md)、[concurrency::parallel\_buffered\_sort](../Topic/parallel_buffered_sort%20Function.md)、および [concurrency::parallel\_radixsort](../Topic/parallel_radixsort%20Function.md) という、PPL に用意されている組み込みの並べ替えアルゴリズムを使用することもできます。  詳細については、「[並列アルゴリズム](../Topic/Parallel%20Algorithms.md)」を参照してください。  
  
##  <a name="top"></a> セクション  
 ここでは、次のタスクについて説明します。  
  
-   [バイトニック ソートを逐次的に実行する](#serial)  
  
-   [parallel\_invoke を使用してバイトニック ソートを並列に実行する](#parallel)  
  
##  <a name="serial"></a> バイトニック ソートを逐次的に実行する  
 次の例は、逐次的なバイトニック ソート アルゴリズムを示しています。  `bitonic_sort` 関数は、シーケンスを 2 つのパーティションに分割し、一方のパーティションは昇順に、もう一方のパーティションは降順に並べ替えた後、その結果をマージします。  この関数は、自分自身を 2 回再帰的に呼び出して、それぞれのパーティションを並べ替えます。  
  
 [!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]  
  
 \[[トップ](#top)\]  
  
##  <a name="parallel"></a> parallel\_invoke を使用してバイトニック ソートを並列に実行する  
 ここでは、`parallel_invoke` アルゴリズムを使用して、バイトニック ソート アルゴリズムを並列に実行する方法について説明します。  
  
### 手順  
  
##### バイトニック ソート アルゴリズムを並列実行するには  
  
1.  ヘッダー ファイル ppl.h の `#include` ディレクティブを追加します。  
  
     [!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]  
  
2.  `concurrency` 名前空間の `using` ディレクティブを追加します。  
  
     [!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]  
  
3.  `parallel_bitonic_mege` という新しい関数を作成します。この関数は、十分な処理量がある場合に、`parallel_invoke` アルゴリズムを使用してシーケンスを並列にマージします。  それ以外の場合は、`bitonic_merge` を呼び出してシーケンスを逐次的にマージします。  
  
     [!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]  
  
4.  前の手順と似たプロセスを実行します \(`bitonic_sort` 関数を除く\)。  
  
     [!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]  
  
5.  配列を昇順に並べ替える `parallel_bitonic_sort` 関数のオーバーロードされたバージョンを作成します。  
  
     [!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]  
  
 `parallel_invoke` アルゴリズムは、オーバーヘッドを低減するために、一連のタスクの最後のタスクを呼び出し元のコンテキストで実行します。  たとえば、`parallel_bitonic_sort` 関数では、1 つ目のタスクは別のコンテキストで実行され、2 つ目のタスクは呼び出し元のコンテキストで実行されます。  
  
 [!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]  
  
 以下に示したのは完成したコード例です。逐次実行版と並列実行版の両方のバイトニック ソート アルゴリズムが実行されます。  この例では、それぞれの計算に要する時間もコンソールに出力します。  
  
 [!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]  
  
 4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。  
  
  **serial time: 4353**  
**parallel time: 1248** \[[トップ](#top)\]  
  
## コードのコンパイル  
 このコードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、`parallel-bitonic-sort.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc parallel\-bitonic\-sort.cpp**  
  
## 信頼性の高いプログラミング  
 それぞれのタスク グループの有効期間が関数を超えることはないため、この例では、[concurrency::task\_group](../Topic/task_group%20Class.md) クラスの代わりに `parallel_invoke` アルゴリズムを使用しています。  `task group` オブジェクトと比べて実行に伴うオーバーヘッドが低く、よりパフォーマンスに優れたコードを記述できるため、できる限り `parallel_invoke` の使用をお勧めします。  
  
 アルゴリズムにもよりますが、並列化によってパフォーマンスの向上が見込めるのは、十分な処理量が存在する場合に限られます。  たとえば、`parallel_bitonic_merge` 関数では、シーケンスに含まれる要素数が 500 未満の場合、逐次実行版の `bitonic_merge` を呼び出すようにしています。  また、処理量に基づいて全体的な並べ替え方法を計画することもできます。  たとえば、次の例に示すように、配列に含まれる項目が 500 未満の場合、逐次実行版のクイック ソート アルゴリズムを使用した方が効率的であることがあります。  
  
 [!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]  
  
 他の並列アルゴリズムと同様に、必要に応じてコードのプロファイリングおよびチューニングを行うことをお勧めします。  
  
## 参照  
 [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [parallel\_invoke 関数](../Topic/parallel_invoke%20Function.md)