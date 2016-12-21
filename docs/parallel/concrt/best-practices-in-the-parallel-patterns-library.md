---
title: "並列パターン ライブラリに関するベスト プラクティス | Microsoft Docs"
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
  - "並列パターン ライブラリ、回避する方法"
  - "並列パターン ライブラリを回避する方法"
  - "ベスト プラクティス、並列パターン ライブラリ"
  - "並列パターン ライブラリ、ベスト プラクティス"
ms.assetid: e43e0304-4d54-4bd8-a3b3-b8673559a9d7
caps.latest.revision: 24
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 並列パターン ライブラリに関するベスト プラクティス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、並列パターン ライブラリ (PPL) を効果的に使用する方法について説明します。 PPL は、粒度の細かい並列化を実行するための汎用的なコンテナー、オブジェクト、およびアルゴリズムを提供します。  
  
 PPL の詳細については、次を参照してください。 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)します。  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> セクション  
 このドキュメントは、次のトピックに分かれています。  
  
- [小さいループ本体を並列化されません。](#small-loops)  
  
- [最高のレベルでの高速の並列処理](#highest)  
  
- [Parallel_invoke 分割統治問題の解決を使用してください。](#divide-and-conquer)  
  
- [キャンセルまたは並列ループを中断する処理の例外を使用します。](#breaking-loops)  
  
- [理解するオブジェクトの破棄に対する取り消しおよび例外処理の影響](#object-destruction)  
  
- [並列ループの繰り返しがブロックされません。](#repeated-blocking)  
  
- [並列処理をキャンセルすると、ブロック操作を実行しないでください。](#blocking)  
  
- [並列ループ内の共有データを書き込めません](#shared-writes)  
  
- [可能であれば、ときに、偽共有しないでください。](#false-sharing)  
  
- [変数が、タスクの有効期間を通じて有効であることを確認します。](#lifetime)  
  
##  <a name="a-namesmall-loopsa-do-not-parallelize-small-loop-bodies"></a><a name="small-loops"></a> 小さいループ本体を並列化されません。  
 比較的小さなループ本体を並列化すると、関連するスケジューリング オーバーヘッドが並列処理のメリットを上回る可能性があります。 次の例について考えます。この例では、2 つの配列に各要素ペアを追加しています。  
  
 [!code-cpp[concrt-small-loops#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_1.cpp)]  
  
 並列ループの各反復の作業負荷が小さすぎるため、並列処理のオーバーヘッドに勝る利益が得られません。 ループ本体での処理量を増やすか、ループを逐次的に実行すると、ループのパフォーマンスが向上します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namehighesta-express-parallelism-at-the-highest-possible-level"></a><a name="highest"></a> 最高のレベルでの高速の並列処理  
 低いレベルでのみコードを並列化する場合は、プロセッサの数が増えても拡張されない fork-join コンストラクトを導入できます。 A *fork と join* コンス トラクターは、コンストラクトの 1 つのタスクが作業をより小さなパラレル サブタスクに分割し、それらのサブタスクを完了するまで待機します。 サブタスクの場合も、それぞれの処理を再帰的に別のサブタスクに分割できます。  
  
 fork-join モデルはさまざまな問題を解決するのに役立ちますが、同期のオーバーヘッドに伴ってスケーラビリティが下がるような状況もあります。 たとえば、イメージ データを逐次的に処理する次のコードについて考えます。  
  
 [!code-cpp[concrt-image-processing-filter#20](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_2.cpp)]  
  
 各ループ反復は独立しているため、次の例に示すように処理の大部分を並列化できます。 この例では、 [concurrency::parallel_for](../Topic/parallel_for%20Function.md) を外側のループを並列化するアルゴリズムです。  
  
 [!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_3.cpp)]  
  
 次の例では、ループで `ProcessImage` 関数を呼び出す fork-join コンストラクトを示します。 `ProcessImage` を呼び出すたびに制御が戻されるのではなく、各サブタスクが終了してから戻されます。  
  
 [!code-cpp[concrt-image-processing-filter#21](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_4.cpp)]  
  
 並列ループの各反復でほとんど処理が実行されないか、並列ループで実行される処理が不均衡の場合 (つまり、ループ反復ごとに所要時間が異なる場合)、処理のフォークと結合を頻繁に行うことによるスケジューリング オーバーヘッドが並列実行のメリットを上回ることがあります。 プロセッサの数が増えると、このオーバーヘッドも大きくなります。  
  
 この例のスケジューリング オーバーヘッドの量を低減するには、内側のループを並列化する前に外側のループを並列化するか、パイプライン処理などの別の parallel コンストラクトを使用します。 次の例では、変更、 `ProcessImages` 関数を使用する、 [concurrency::parallel_for_each](../Topic/parallel_for_each%20Function.md) 外側のループを並列化にします。  
  
 [!code-cpp[concrt-image-processing-filter#22](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_5.cpp)]  
  
 パイプラインを使用して並列でイメージ処理を実行するような例を参照してください。 [チュートリアル: イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namedivide-and-conquera-use-parallelinvoke-to-solve-divide-and-conquer-problems"></a><a name="divide-and-conquer"></a> Parallel_invoke 分割統治問題の解決を使用してください。  
 A *分割統治* 問題は、再帰を使用して、タスクをサブタスクに分割する fork と join コンストラクトの形式です。 加え、 [concurrency::task_group](../Topic/task_group%20Class.md) と [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) クラスを使用することも、 [concurrency::parallel_invoke](../Topic/parallel_invoke%20Function.md) 分割統治の問題を解決するアルゴリズムです。 `parallel_invoke` アルゴリズムでは、タスク グループ オブジェクトよりも簡単な構文を使用できます。このアルゴリズムは、並列タスクの数が固定されている場合に役立ちます。  
  
 次の例では、`parallel_invoke` アルゴリズムを使用して、バイトニック ソート アルゴリズムを実装します。  
  
 [!code-cpp[concrt-parallel-bitonic-sort#12](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_6.cpp)]  
  
 `parallel_invoke` アルゴリズムでは、オーバーヘッドを低減するために、一連のタスクの最後のタスクを呼び出し元のコンテキストで実行します。  
  
 この例の完全なバージョンは、 [方法: parallel.invoke を使用して並列並べ替えルーチンを記述する](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)です。 詳細については、 `parallel_invoke` アルゴリズムを参照してください [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namebreaking-loopsa-use-cancellation-or-exception-handling-to-break-from-a-parallel-loop"></a><a name="breaking-loops"></a> キャンセルまたは並列ループを中断する処理の例外を使用します。  
 PPL では、2 とおりの方法を使用して、タスク グループまたは並列アルゴリズムによって実行される並列処理を取り消すことができます。 によって提供されるキャンセル メカニズムを使用する方法の 1 つは、 [concurrency::task_group](../Topic/task_group%20Class.md) と [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) クラスです。 もう 1 つは、タスクの処理関数の本体で例外をスローする方法です。 並列処理ツリーを取り消す場合は、例外処理を行うよりも取り消し機構を使用する方が効率的です。 A *並列処理ツリー* いくつかのタスク グループが別のタスク グループを含む関連するタスク グループのグループです。 取り消し機構では、タスク グループとその子タスク グループを上位から順に取り消します。 反対に、例外処理では下位から順に処理されるため、例外が上位へ移動するたびに、子タスク グループを個別に取り消す必要があります。  
  
 タスク グループ オブジェクトを直接操作するときに使用して、 [:cancel](../Topic/task_group::cancel%20Method.md) または [concurrency::structured_task_group::cancel](../Topic/structured_task_group::cancel%20Method.md) タスク グループに属している処理を取り消す方法です。 たとえば、`parallel_for` では、並列アルゴリズムを取り消すために、親タスク グループを作成し、そのタスク グループを取り消します。 たとえば、次の関数 `parallel_find_any` について考えます。この関数では、配列内の値を並列に検索します。  
  
 [!code-cpp[concrt-parallel-array-search#2](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_7.cpp)]  
  
 並列アルゴリズムではタスク グループが使用されるため、並列反復処理のいずれかによって親タスク グループが取り消されると、タスク全体が取り消されます。 この例の完全なバージョンは、 [方法: 並列ループに取り消し中断を使用する](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)です。  
  
 例外処理を使用して並列処理を取り消す方法は、取り消し機構を使用する方法よりも効率の面で劣りますが、例外処理の方が適している状況もあります。 たとえば、次のメソッド `for_all` では、`tree` 構造体の各ノードに対して処理関数を再帰的に実行します。 この例では、 `_children` データ メンバーは、 [std::list](../../standard-library/list-class.md) を含む `tree` オブジェクトです。  
  
 [!code-cpp[concrt-task-tree-search#6](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_8.cpp)]  
  
 ツリーの各要素に対して処理関数を呼び出す必要がない場合、`tree::for_all` メソッドの呼び出し元は例外をスローすることができます。 次の例は `search_for_value` 関数で、提供された `tree` オブジェクト内で値を検索します。 `search_for_value` 関数で使用される処理関数は、ツリーの現在の要素と提供された値が一致する場合に例外をスローします。 `search_for_value` 関数は、`try-catch` ブロックを使用して例外をキャプチャし、結果をコンソールに出力します。  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_9.cpp)]  
  
 この例の完全なバージョンは、 [方法: 使用する例外処理を中断する並列ループ](../Topic/How%20to:%20Use%20Exception%20Handling%20to%20Break%20from%20a%20Parallel%20Loop.md)します。  
  
 取り消しおよび例外処理機構、PPL によって提供されるより一般的なについては、次を参照してください。 [キャンセル](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md#cancellation_in_the_ppl) と [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-nameobject-destructiona-understand-how-cancellation-and-exception-handling-affect-object-destruction"></a><a name="object-destruction"></a> 理解するオブジェクトの破棄に対する取り消しおよび例外処理の影響  
 並列処理ツリーでタスクを取り消すと、子タスクも実行されなくなります。 そのため、アプリケーションで重要となる操作 (リソースの解放など) が子タスクのいずれかで実行されるような場合に問題となります。 また、タスクを取り消すと、例外がオブジェクトのデストラクターを通じて反映され、アプリケーションで未定義の動作が発生する可能性があります。  
  
 次の例では、`Resource` クラスはリソースを表し、`Container` クラスはリソースを保持するコンテナーを表します。 そのデストラクターで、`Container` クラスは `Resource` メンバーの 2 つに対して `cleanup` メソッドを並列に呼び出し、3 つ目の `Resource` メンバーに対して `cleanup` メソッドを呼び出します。  
  
 [!code-cpp[concrt-parallel-resource-destruction#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_10.h)]  
  
 このパターン自体には問題はありませんが、2 つのタスクを並列に実行する次のコードについて考えてみてください。 1 つ目のタスクでは `Container` オブジェクトを作成し、2 つ目のタスクではタスク全体を取り消します。 図では、例では、2 つ使用して [concurrency::event](../Topic/event%20Class.md) 後に、キャンセルが発生することを確認するオブジェクト、 `Container` オブジェクトが作成されると、 `Container` 取り消し操作が発生した後、オブジェクトが破棄されます。  
  
 [!code-cpp[concrt-parallel-resource-destruction#2](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_11.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
Container 1: Freeing resources...Exiting program...  
```  
  
 このコード例には次の問題が含まれているため、期待どおりの動作が得られない可能性があります。  
  
-   親タスクのキャンセルと子タスクの呼び出しを [concurrency::parallel_invoke](../Topic/parallel_invoke%20Function.md), を取り消すこともできます。 そのため、これら 2 つのリソースは解放されません。  
  
-   親タスクを取り消すと、子タスクが内部例外をスローします。 `Container` デストラクターではこの例外は処理されないため、例外が上位に伝達され、3 つ目のリソースは解放されません。  
  
-   子タスクによってスローされた例外が、`Container` デストラクターを通じて伝達されます。 デストラクターからスローされることにより、アプリケーションが未定義の状態になります。  
  
 タスクが取り消されないことを保証できる場合を除き、タスクでは重要な操作 (リソースの解放など) を実行しないことをお勧めします。 また、採用している型のデストラクターでスローを行うようなランタイム機能は使用しないようにしてください。  
  
 [[トップ](#top)]  
  
##  <a name="a-namerepeated-blockinga-do-not-block-repeatedly-in-a-parallel-loop"></a><a name="repeated-blocking"></a> 並列ループの繰り返しがブロックされません。  
 など、並列ループ [concurrency::parallel_for](../Topic/parallel_for%20Function.md) または [concurrency::parallel_for_each](../Topic/parallel_for_each%20Function.md) はブロックすることによって左右されますが発生したか、ランタイムを短時間で多数のスレッドを作成します。  
  
 同時実行ランタイムでは、タスクが終了するか、協調的にブロックまたは譲渡すると、追加の処理が実行されます。 並列ループの 1 回の反復がブロックすると、別の反復が開始されることがあります。 使用可能なアイドル スレッドが存在しない場合は、新しいスレッドが作成されます。  
  
 並列ループの本体がときどきブロックする程度であれば、この機構によりタスクの全体的なスループットが最大限に高まります。 ただし、反復処理で頻繁にブロックが発生する場合は、追加の処理を実行するために多数のスレッドが作成される可能性があります。 それに伴って、メモリ不足の状態に陥ったり、ハードウェア リソースが不適切に使用されたりする場合があります。  
  
 呼び出す次の例を検討してください、 [concurrency::send](../Topic/send%20Function.md) 関数の各反復で、 `parallel_for` ループします。 `send` は協調的にブロックするため、`send` を呼び出すたびに、追加の処理を実行するための新しいスレッドが作成されます。  
  
 [!code-cpp[concrt-repeated-blocking#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_12.cpp)]  
  
 このパターンを回避するようにコードをリファクタリングすることをお勧めします。 この例では、逐次的な `for` ループで `send` を呼び出すことによって、追加のスレッドの作成を回避できます。  
  
 [[トップ](#top)]  
  
##  <a name="a-nameblockinga-do-not-perform-blocking-operations-when-you-cancel-parallel-work"></a><a name="blocking"></a> 並列処理をキャンセルすると、ブロック操作を実行しないでください。  
 可能であれば、操作が実行されないブロックを呼び出す前に、 [:cancel](../Topic/task_group::cancel%20Method.md) または [concurrency::structured_task_group::cancel](../Topic/structured_task_group::cancel%20Method.md) 並列処理を取り消す方法です。  
  
 タスクが協調的ブロッキング操作を実行すると、ランタイムは最初のタスクがデータを待っている間に他の処理を実行できます。 待機中のタスクがブロック解除すると、ランタイムはそのタスクを再スケジュールします。 ランタイムは、通常、直近にブロック解除したタスクから順に再スケジュールします。 そのため、ブロッキング操作中に不要な処理がスケジュールされ、パフォーマンスが低下します。 したがって、並列処理を取り消す前にブロッキング操作を実行すると、そのブロッキング操作が原因で `cancel` の呼び出しが遅れる可能性があります。 それにより、他のタスクで不要な処理が実行されるようになります。  
  
 次の例について考えます。この例では、提供された述語関数を満たす指定の配列の要素を検索する `parallel_find_answer` 関数を定義します。 述語関数が `true` を返すと、並列処理関数は `Answer` オブジェクトを作成し、タスク全体を取り消します。  
  
 [!code-cpp[concrt-blocking-cancel#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_13.cpp)]  
  
 `new` 演算子は、ブロッキングの対象となる可能性のあるヒープ割り当てを実行します。 ランタイムがタスクへの呼び出しなどの呼び出しをブロックして共同を実行する場合にのみ、その他の作業を実行 [concurrency::critical_section::lock](../Topic/critical_section::lock%20Method.md)します。  
  
 次の例では、不要な処理を回避し、それによってパフォーマンスを向上させる方法を示します。 この例では、`Answer` オブジェクト用のストレージを割り当てる前に、タスク グループを取り消します。  
  
 [!code-cpp[concrt-blocking-cancel#2](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_14.cpp)]  
  
 [[トップ](#top)]  
  
##  <a name="a-nameshared-writesa-do-not-write-to-shared-data-in-a-parallel-loop"></a><a name="shared-writes"></a> 並列ループ内の共有データを書き込めません  
 たとえば、同時実行ランタイムにいくつかのデータ構造が用意されています [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), 、共有データへの同時アクセスを同期します。 これらのデータ構造体は、複数のタスクでリソースへの共有アクセスがまれに必要になる場合など、さまざまな状況で役立ちます。  
  
 使用して次の例を検討してください、 [concurrency::parallel_for_each](../Topic/parallel_for_each%20Function.md) アルゴリズムと `critical_section` オブジェクトに含まれる素数の数を計算する [std::array](../../standard-library/array-class-stl.md) オブジェクトです。 この例では、各スレッドが共有変数 `prime_sum` にアクセスするのを待つ必要があるため、効率は改善されません。  
  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_15.cpp)]  
  
 また、頻繁なロック操作によってループが事実上シリアル化されるため、パフォーマンスが低下する可能性もあります。 さらに、同時実行ランタイム オブジェクトがブロック操作を実行すると、スケジューラによって追加のスレッドが作成され、最初のスレッドがデータを待っている間に他の処理が実行される可能性があります。 共有データを待つタスクが多数存在し、それに対処するためにランタイムで多数のスレッドが作成されると、アプリケーションのパフォーマンス低下やリソース不足状態が発生することがあります。  
  
 PPL の定義、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) クラスは、ロック制御不要の方法で共有リソースへのアクセスを提供することで、共有状態を回避できます。 `combinable` クラスにはスレッド ローカル ストレージが用意されており、詳細な計算を実行した後、その計算を最終結果にマージできます。 `combinable` オブジェクトは減少変数と考えることができます。  
  
 次の例では、前の例を変更し、合計を計算するときに `critical_section` オブジェクトの代わりに `combinable` オブジェクトを使用するようにしています。 この例では、各スレッドが合計のローカル コピーをそれぞれ保持するため、効率が改善されます。 この例では、 [concurrency::combinable::combine](../Topic/combinable::combine%20Method.md) メソッドをローカルの計算を最終結果にマージします。  
  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_16.cpp)]  
  
 この例の完全なバージョンは、 [方法: パフォーマンスを改善する combinable を使用して](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)します。 詳細については、 `combinable` を参照してください [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namefalse-sharinga-when-possible-avoid-false-sharing"></a><a name="false-sharing"></a> 可能であれば、ときに、偽共有しないでください。  
 *偽共有* 別のプロセッサで実行されている複数の同時実行タスクが同じキャッシュ ラインに配置されている変数に書き込むときに発生します。 1 つのタスクが変数のいずれかに書き込みを行うと、両方の変数のキャッシュ ラインが無効化されます。 キャッシュ ラインが無効化されるたびに、各プロセッサでキャッシュ ラインの再読み込みを行う必要があります。 したがって、偽共有が発生すると、アプリケーションでパフォーマンスが低下する可能性があります。  
  
 次の基本的な例では、2 つの同時実行タスクがそれぞれ共有カウンター変数をインクリメントする場合を示します。  
  
 [!code-cpp[concrt-false-sharing#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_17.cpp)]  
  
 2 つのタスク間でデータが共有されないようにするには、2 つのカウンター変数を使用するように例を変更します。 この例では、タスクの終了後に最終的なカウンター値を計算します。 ただし、`count1` 変数と `count2` 変数が同じキャッシュ ラインに配置される可能性があるため、偽共有となります。  
  
 [!code-cpp[concrt-false-sharing#2](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_18.cpp)]  
  
 偽共有をなくす方法の 1 つは、カウンター変数を必ず別々のキャッシュ ラインに配置することです。 次の例では、64 バイト境界上に `count1` 変数と `count2` 変数を配置します。  
  
 [!code-cpp[concrt-false-sharing#3](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_19.cpp)]  
  
 この例では、メモリ キャッシュのサイズが 64 バイト以下であると仮定しています。  
  
 使用することをお勧めします [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) 時、タスク間でデータを共有する必要があります。 `combinable` クラスは、偽共有が発生する可能性を減らすようにスレッド ローカル変数を作成します。 詳細については、 `combinable` を参照してください [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namelifetimea-make-sure-that-variables-are-valid-throughout-the-lifetime-of-a-task"></a><a name="lifetime"></a> 変数が、タスクの有効期間を通じて有効であることを確認します。  
 タスク グループまたは並列アルゴリズムにラムダ式を渡す場合、ラムダ式の本体で外側のスコープ内の変数を値でアクセスするのか参照でアクセスするのかは、capture 句で指定します。 ラムダ式に変数を渡すときに参照渡しを使用する場合、タスクが終了するまでその変数の有効期間が続くようにする必要があります。  
  
 次の例について考えます。この例では、`object` クラスと `perform_action` 関数を定義します。 `perform_action` 関数は、`object` 変数を作成し、その変数に対していくつかのアクションを非同期的に実行します。 `perform_action` 関数から制御が戻される前にタスクが終了するとは限らないため、タスクの実行中に `object` 変数が破棄されると、プログラムのクラッシュや未定義の動作が発生します。  
  
 [!code-cpp[concrt-lambda-lifetime#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_20.cpp)]  
  
 アプリケーションの要件に応じて、次の手法のいずれかを使用して、変数が各タスクの有効期間を通じて有効のまま維持されるようにすることができます。  
  
 次の例では、タスクに対して `object` 変数の値渡しを行います。 そのため、タスクは変数の個別コピーに対して作用します。  
  
 [!code-cpp[concrt-lambda-lifetime#2](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_21.cpp)]  
  
 `object` 変数は値渡しで渡されるため、この変数の状態変化が発生しても、元のコピーには反映されません。  
  
 次の例では、 [:wait](../Topic/task_group::wait%20Method.md) 前に、タスクが終了するかどうかを確認するメソッド、 `perform_action` 関数が返される。  
  
 [!code-cpp[concrt-lambda-lifetime#3](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_22.cpp)]  
  
 関数から制御が戻される前にタスクが終了するようになったため、`perform_action` 関数が非同期に動作することがなくなりました。  
  
 次の例では、`perform_action` 関数を変更して、`object` 変数の参照が使用されるようにします。 呼び出し元は、タスクが終了するまで `object` 変数の有効期間が続くようにする必要があります。  
  
 [!code-cpp[concrt-lambda-lifetime#4](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-parallel-patterns-library_23.cpp)]  
  
 また、タスク グループまたは並列アルゴリズムに渡すオブジェクトの有効期間をポインターで制御することもできます。  
  
 ラムダ式の詳細については、次を参照してください。 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)します。  
  
 [[トップ](#top)]  
  
## <a name="see-also"></a>「  
 [同時実行ランタイムに関するベスト プラクティスします。](../Topic/Concurrency%20Runtime%20Best%20Practices.md)   
 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)   
 [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)   
 [キャンセル](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md#cancellation_in_the_ppl)   
 [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)   
 [チュートリアル: イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [方法: parallel.invoke を使用して並列並べ替えルーチンを記述するには](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)   
 [方法: キャンセルを使用して並列ループを中断する](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)   
 [方法: パフォーマンスを改善する combinable を使用して](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)   
 [非同期エージェント ライブラリに関するベスト プラクティス](../Topic/Best%20Practices%20in%20the%20Asynchronous%20Agents%20Library.md)   
 [同時実行ランタイムでの一般的なベスト プラクティス](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)

