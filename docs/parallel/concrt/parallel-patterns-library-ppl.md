---
title: "並列パターン ライブラリ (PPL) | Microsoft Docs"
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
  - "並列パターン ライブラリ (PPL)"
ms.assetid: 40fd86b2-69fa-45e5-93d8-98a75636c242
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# 並列パターン ライブラリ (PPL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

並列パターン ライブラリ (PPL: Parallel Patterns Library) は、同時実行アプリケーションの開発に不可欠な、スケーラビリティが高く使いやすいプログラミング モデルを提供します。 PPL は、同時実行ランタイムのスケジューリング コンポーネントとリソース管理コンポーネントに基づいています。 PPL には、データを並列的に操作する、タイプ セーフのジェネリックなアルゴリズムとコンテナーが用意されています。これらを使用すると、アプリケーション コードと基になるスレッド処理機構の間で抽象化のレベルを引き上げることができます。 また、PPL には共有状態に代わる手段が用意されているため、規模の変更に対応したアプリケーションの開発にも役立ちます。  
  
 PPL には次の機能があります。  
  
- *タスクの並列処理*: いくつかの作業項目 (タスク) を並列に実行する Windows のスレッド プール上で動作するためのメカニズム  
  
- *並列アルゴリズム*: 並列でデータのコレクションに対して機能する同時実行ランタイム上で動作するジェネリックなアルゴリズム  
  
- *並列コンテナーと並列オブジェクト*: その要素への安全な同時アクセスを提供するジェネリックなコンテナーの種類  
  
## <a name="example"></a>例  
 PPL には、標準テンプレート ライブラリ (STL) に似たプログラミング モデルが用意されています。 次の例では、PPL のさまざまな機能を示します。 複数のフィボナッチの数列を逐次的および並列的に計算します。 それぞれの計算処理、 [std::array](../../standard-library/array-class-stl.md) オブジェクトです。 また、それぞれの計算に要する時間もコンソールに出力します。  
  
 逐次実行版は、STL を使用して [std::for_each](../Topic/for_each.md) 配列を走査するアルゴリズムの結果を格納し、 [std::vector](../../standard-library/vector-class.md) オブジェクトです。 並列バージョンは同じタスクを実行しますが、PPL を使用して [concurrency::parallel_for_each](../Topic/parallel_for_each%20Function.md) アルゴリズムの結果を格納し、 [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) オブジェクトです。 `concurrent_vector` クラスを使用することで、コンテナーへの書き込みアクセスを同期しなくても各ループ反復で要素を同時に追加できます。  
  
 `parallel_for_each` は同時に処理を行うため、この例の並列バージョンでは、`concurrent_vector` オブジェクトを並べ替え、逐次バージョンと同じ結果を生成する必要があります。  
  
 この例では、素朴な方法を使用してフィボナッチの数列を計算しています。ただし、この方法で示しているのは、同時実行ランタイムによって長い計算のパフォーマンスが向上するしくみです。  
  
 [!code-cpp[concrt-parallel-fibonacci#1](../../parallel/concrt/codesnippet/CPP/parallel-patterns-library-ppl_1.cpp)]  
  
 4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。  
  
```Output  
serial time: 9250 ms  
parallel time: 5726 ms  
 
fib(24): 46368  
fib(26): 121393  
fib(41): 165580141  
fib(42): 267914296  
```  
  
 終了までに要する時間は、ループ反復ごとに異なります。 `parallel_for_each` のパフォーマンスは最後に終了した操作に関係してくるため、 この例の逐次バージョンと並列バージョンを比べても、パフォーマンスのリニアな向上は期待できません。  
  
## <a name="related-topics"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|PPL でのタスクおよびタスク グループの役割について説明します。|  
|[並列アルゴリズム](../Topic/Parallel%20Algorithms.md)|`parallel_for` や `parallel_for_each` などの並列アルゴリズムの使用方法について説明します。|  
|[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)|PPL に用意されているさまざまな並列コンテナーと並列オブジェクトについて説明します。|  
|[キャンセル](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md#cancellation_in_the_ppl)|並列アルゴリズムによって行われている処理を取り消す方法について説明します。|  
|[同時実行ランタイム](../../parallel/concrt/concurrency-runtime.md)|並列プログラミングを容易にする同時実行ランタイムについて説明します。また、関連トピックへのリンクを示します。|

