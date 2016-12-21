---
title: "非同期メッセージ ブロック | Microsoft Docs"
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
  - "最短一致の結合 [同時実行ランタイム]"
  - "非同期メッセージ ブロック"
  - "最長一致の結合 [同時実行ランタイム]"
ms.assetid: 79c456c0-1692-480c-bb67-98f2434c1252
caps.latest.revision: 36
caps.handback.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 非同期メッセージ ブロック
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エージェント ライブラリには、アプリケーション コンポーネント間でメッセージをスレッド セーフに伝達できるメッセージ ブロックの型がいくつか用意されています。 これらのメッセージ ブロックの型はなど、さまざまなメッセージ パッシング ルーチンと共に使用多くの場合、 [concurrency::send](../Topic/send%20Function.md), 、[concurrency::asend](../Topic/asend%20Function.md), 、[concurrency::receive](../Topic/receive%20Function.md), 、および [concurrency::try_receive](../Topic/try_receive%20Function.md)します。 詳細については、メッセージ パッシング ルーチンのエージェント ライブラリによって定義されている、次を参照してください。 [メッセージを渡す関数](../../parallel/concrt/message-passing-functions.md)します。  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> セクション  
 このトピックは、次のセクションで構成されています。  
  
- [ソースとターゲット](#sources_and_targets)  
  
- [メッセージの伝達](#propagation)  
  
- [メッセージ ブロックの型の概要](#overview)  
  
- [unbounded_buffer クラス](#unbounded_buffer)  
  
- [overwrite_buffer クラス](#overwrite_buffer)  
  
- [single_assignment クラス](#single_assignment)  
  
- [クラスを呼び出します。](#call)  
  
- [transformer クラス](#transformer)  
  
- [choice クラス](#choice)  
  
- [join クラスと multitype_join クラス](#join)  
  
- [timer クラス](#timer)  
  
- [メッセージのフィルター処理](#filtering)  
  
- [メッセージの予約](#reservation)  
  
##  <a name="a-namesourcesandtargetsa-sources-and-targets"></a><a name="sources_and_targets"></a> ソースとターゲット  
 ソースとターゲットは、メッセージ パッシングの 2 つの重要な参加要素です。 A *ソース* メッセージを送信する通信のエンドポイントを参照します。 A *ターゲット* メッセージを受信する通信のエンドポイントを参照します。 ソースは読み取るエンドポイントであり、ターゲットは書き込むエンドポイントであると考えることができます。 アプリケーションがフォームにソースとターゲットの同時接続 *メッセージング ネットワーク*します。  
  
 エージェント ライブラリでは、2 つの抽象クラスを使用して、ソースとターゲットを表す: [concurrency::isource](../../parallel/concrt/reference/isource-class.md) と [concurrency::itarget](../../parallel/concrt/reference/itarget-class.md)します。 ソースとして機能するメッセージ ブロックの型は `ISource` から派生します。ターゲットとして機能するメッセージ ブロックの型は `ITarget` から派生します。 ソースおよびターゲットとして機能するメッセージ ブロックの型は、それぞれ `ISource` および `ITarget` から派生します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namepropagationa-message-propagation"></a><a name="propagation"></a> メッセージの伝達  
 *メッセージの伝達* は 1 つのコンポーネント間でメッセージを送信する行為。 メッセージ ブロックにメッセージが提供されると、そのメッセージ ブロックはメッセージを受け入れるか、拒否するか、または延期します。 各メッセージ ブロックの型は、さまざまな方法でメッセージを格納および送信します。 たとえば、`unbounded_buffer` クラスはメッセージを無制限に格納し、`overwrite_buffer` クラスは一度に 1 つのメッセージを格納し、transformer クラスは各メッセージの変更後のバージョンを格納します。 これらのメッセージ ブロックの型については、このドキュメントの後半で詳しく説明します。  
  
 メッセージ ブロックは、メッセージを受け入れるとき、必要に応じて処理を実行できます。メッセージ ブロックがソースである場合は、結果のメッセージをネットワークの別のメンバーに渡します。 メッセージ ブロックは、フィルター関数を使用して、不要なメッセージを拒否できます。 フィルターの後のセクションで、このトピックで詳しくは「 [メッセージのフィルター処理](#filtering)します。 メッセージを延期するメッセージ ブロックは、そのメッセージを予約しておいて後で処理できます。 メッセージの予約の詳細セクションで、このトピックの後半に記載されている [メッセージの予約](#reservation)します。  
  
 エージェント ライブラリを使用すると、メッセージ ブロックによってメッセージを非同期的に渡すことも、同期的に渡すこともできます。 `send` 関数などを使用してメッセージを同期的にメッセージ ブロックに渡すと、ターゲット ブロックがそのメッセージを受け入れるか拒否するまで、ランタイムは現在のコンテキストをブロックします。 `asend` 関数などを使用してメッセージを非同期的にメッセージ ブロックに渡すと、ランタイムはそのメッセージをターゲットに提供します。ターゲットがそのメッセージを受け入れると、ランタイムはメッセージを受信側に伝達する非同期タスクをスケジュールします。 ランタイムは、軽量タスクを使用して、メッセージを協調的に伝達します。 軽量タスクの詳細については、次を参照してください。 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。  
  
 アプリケーションでは、ソースとターゲットを接続することでメッセージング ネットワークを形成します。 通常、ネットワークをリンクし、`send` または `asend` を呼び出してデータをネットワークに渡します。 ソース メッセージ ブロックをターゲットに接続するには、呼び出し、 [concurrency::ISource::link_target](../Topic/ISource::link_target%20Method.md) メソッドです。 ターゲットからソース ブロックを切断するを呼び出す、 [concurrency::ISource::unlink_target](../Topic/ISource::unlink_target%20Method.md) メソッドです。 すべてのターゲットをソース ブロックを切断するを呼び出す、 [concurrency::ISource::unlink_targets](../Topic/ISource::unlink_targets%20Method.md) メソッドです。 定義済みのメッセージ ブロックの型のいずれかがスコープから外れるか、破棄されると、自動的にすべてのターゲット ブロックから接続解除されます。 メッセージ ブロックの型の中には、書き込み先として使用できるターゲットの最大数が制限されているものもあります。 次のセクションでは、定義済みのメッセージ ブロックの型に適用される制限事項について説明します。  
  
 [[トップ](#top)]  
  
##  <a name="a-nameoverviewa-overview-of-message-block-types"></a><a name="overview"></a> メッセージ ブロックの型の概要  
 次の表では、重要なメッセージ ブロックの型の役割について簡単に説明しています。  
  
 [unbounded_buffer](#unbounded_buffer)  
 メッセージのキューを格納します。  
  
 [overwrite_buffer](#overwrite_buffer)  
 複数回の書き込みと読み取りを行うことができるメッセージを 1 つ格納します。  
  
 [single_assignment](#single_assignment)  
 1 回の書き込みと複数回の読み取りを行うことができるメッセージを 1 つ格納します。  
  
 [呼び出し](#call)  
 メッセージを受信するときに処理を実行します。  
  
 [(トランスフォーマーを)](#transformer)  
 データを受け取り、その処理の結果を別のターゲット ブロックに送信するときに処理を実行します。 `transformer` クラスでは、異なる入力と出力の種類を操作できます。  
  
 [選択肢](#choice)  
 一連のソースから最初の使用可能なメッセージを選択します。  
  
 [join と multitype join](#join)  
 一連のソースからすべてのメッセージを受信するまで待機し、別のメッセージ ブロックのために、複数のメッセージを結合して 1 つのメッセージにします。  
  
 [タイマー](#timer)  
 メッセージを定期的にターゲット ブロックに送信します。  
  
 これらのメッセージ ブロックの型には、それぞれ異なる状況で役立つ特性があります。 その特性のいくつかを次に示します。  
  
- *伝達の種類*: メッセージ ブロックはデータ、データの受信側のソースとして機能するかどうか。  
  
- *メッセージの順序付け*: メッセージ ブロックがメッセージを送信または受信は、元の順序を保持するかどうか。 定義済みのメッセージ ブロックの型では、メッセージが送受信されたときの元の順序が保持されます。  
  
- *ソース カウント*: メッセージ ブロックがから読み取ることができるソースの最大数。  
  
- *ターゲット カウント*: メッセージ ブロックにデータを書き込むターゲットの最大数。  
  
 これらの特性とさまざまなメッセージ ブロックの型の関係を次の表に示します。  
  
|メッセージ ブロックの型|伝達の種類 (ソース、ターゲット、または両方)|メッセージの順序付け (順序ありまたは順序なし)|ソース カウント|ターゲット カウント|  
|------------------------|--------------------------------------------------|-----------------------------------------------|------------------|------------------|  
|`unbounded_buffer`|両方|順序あり|制限なし|制限なし|  
|`overwrite_buffer`|両方|順序あり|制限なし|制限なし|  
|`single_assignment`|両方|順序あり|制限なし|制限なし|  
|`call`|Target|順序あり|制限なし|適用できません|  
|`transformer`|両方|順序あり|制限なし|1|  
|`choice`|両方|順序あり|10|1|  
|`join`|両方|順序あり|制限なし|1|  
|`multitype_join`|両方|順序あり|10|1|  
|`timer`|ソース|該当せず|該当せず|1|  
  
 以下のセクションでは、メッセージ ブロックの型について詳しく説明します。  
  
 [[トップ](#top)]  
  
##  <a name="a-nameunboundedbuffera-unboundedbuffer-class"></a><a name="unbounded_buffer"></a> unbounded_buffer クラス  
  [Concurrency::unbounded_buffer](../Topic/unbounded_buffer%20Class.md) クラスは汎用的な非同期メッセージング構造体を表します。 このクラスでは、複数のソースが書き込むことができるメッセージ、または複数のターゲットが読み取ることができるメッセージの先入れ先出し (FIFO) のキューを格納します。 ターゲットが `unbounded_buffer` オブジェクトからメッセージを受信すると、そのメッセージはメッセージ キューから削除されます。 そのため、`unbounded_buffer` オブジェクトには複数のターゲットを設定できますが、各メッセージを受信するターゲットは 1 つだけです。 `unbounded_buffer` クラスは、複数のメッセージを別のコンポーネントに渡し、そのコンポーネントで各メッセージを受信する必要がある場合に便利です。  
  
### <a name="example"></a>例  
 次の例では、`unbounded_buffer` クラスの使用方法の基本的な構造を示します。 この例では、3 つの値を `unbounded_buffer` オブジェクトに送信し、同じオブジェクトからそれらの値を再び読み取ります。  
  
 [!code-cpp[concrt-unbounded_buffer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
334455  
```  
  
 使用する方法を示す完全な例については、 `unbounded_buffer` を参照してください [方法: さまざまなプロデューサー/コンシューマー パターンを実装する](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="a-nameoverwritebuffera-overwritebuffer-class"></a><a name="overwrite_buffer"></a> overwrite_buffer クラス  
  [Concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) クラスに似ています、 `unbounded_buffer` クラスのことを除いて、 `overwrite_buffer` オブジェクトは 1 つのメッセージを格納します。 また、ターゲットが `overwrite_buffer` オブジェクトからメッセージを受信しても、そのメッセージはバッファーから削除されません。 そのため、複数のターゲットがメッセージのコピーを受信します。  
  
 `overwrite_buffer` クラスは、複数のメッセージを別のコンポーネントに渡すときに、そのコンポーネントで必要になるのが最新の値のみである場合に便利です。 また、このクラスは、メッセージを複数のコンポーネントにブロードキャストする場合にも便利です。  
  
### <a name="example"></a>例  
 次の例では、`overwrite_buffer` クラスの使用方法の基本的な構造を示します。 この例では、3 つの値を `overwrite _buffer` オブジェクトに送信し、同じオブジェクトから現在の値を 3 回読み取ります。 この例は `unbounded_buffer` クラスの例に似ています。 ただし、`overwrite_buffer` クラスに格納されるメッセージは 1 つだけです。 また、メッセージが読み取られた後も、`overwrite_buffer` オブジェクトからそのメッセージは削除されません。  
  
 [!code-cpp[concrt-overwrite_buffer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_2.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
555555  
```  
  
 使用する方法を示す完全な例については、 `overwrite_buffer` を参照してください [方法: さまざまなプロデューサー/コンシューマー パターンを実装する](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="a-namesingleassignmenta-singleassignment-class"></a><a name="single_assignment"></a> single_assignment クラス  
  [Concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) クラスに似ています、 `overwrite_buffer` クラスのことを除いて、 `single_assignment` オブジェクトに 1 回しか書き込むことができます。 `overwrite_buffer` クラスと同様に、ターゲットが `single_assignment` オブジェクトからメッセージを受信しても、そのメッセージはそのオブジェクトから削除されません。 そのため、複数のターゲットがメッセージのコピーを受信します。 また、`single_assignment` クラスは、1 つのメッセージを複数のコンポーネントにブロードキャストする場合にも便利です。  
  
### <a name="example"></a>例  
 次の例では、`single_assignment` クラスの使用方法の基本的な構造を示します。 この例では、3 つの値を `single_assignment` オブジェクトに送信し、同じオブジェクトから現在の値を 3 回読み取ります。 この例は `overwrite_buffer` クラスの例に似ています。 `overwrite_buffer` クラスおよび `single_assignment` クラスに格納されるメッセージはどちらの場合も 1 つだけですが、`single_assignment` クラスには 1 回しか書き込むことができません。  
  
 [!code-cpp[concrt-single_assignment-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_3.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
333333  
```  
  
 使用する方法を示す完全な例については、 `single_assignment` を参照してください [チュートリアル: フューチャの実装](../../parallel/concrt/walkthrough-implementing-futures.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namecalla-call-class"></a><a name="call"></a> クラスを呼び出します。  
  [Concurrency::call](../../parallel/concrt/reference/call-class.md) クラスはデータを受信したときに、処理関数を実行するメッセージの受信側として機能します。 この処理関数には、ラムダ式、関数オブジェクト、または関数ポインターを使用できます。 `call` オブジェクトは、メッセージを送信する他のコンポーネントに対して並列に動作するため、通常の関数呼び出しとは動作が異なります。 `call` オブジェクトがメッセージを受信したときに処理を実行していると、そのメッセージはキューに追加されます。 各 `call` オブジェクトでは、キューに配置されたメッセージを受信した順序で処理します。  
  
### <a name="example"></a>例  
 次の例では、`call` クラスの使用方法の基本的な構造を示します。 この例では、受信した各値をコンソールに出力する `call` オブジェクトを作成します。 その後、3 つの値を `call` オブジェクトに送信します。  `call` オブジェクトが別のスレッドでメッセージを処理します。 この例では、カウンター変数も使用して、および [イベント](../Topic/event%20Class.md) いることを確認するオブジェクト、 `call` オブジェクトを処理する前にすべてのメッセージ、 `wmain` 関数が返される。  
  
 [!code-cpp[concrt-call-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_4.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
334455  
```  
  
 使用する方法を示す完全な例については、 `call` を参照してください [方法: 処理関数の呼び出しおよび transformer クラスを提供](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-nametransformera-transformer-class"></a><a name="transformer"></a> transformer クラス  
  [Concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) クラスは、両方のメッセージの受信者、およびメッセージの送信者として機能します。 `transformer` クラスは、データを受信するとユーザー定義の処理関数を実行するため、`call` クラスに似ています。 ただし、`transformer` クラスも処理関数の結果を受信側のオブジェクトに送信します。 `call` オブジェクトと同様に、`transformer` オブジェクトはメッセージを送信する他のコンポーネントに対して並列に動作します。 `transformer` オブジェクトがメッセージを受信したときに処理を実行していると、そのメッセージはキューに追加されます。 各 `transformer` オブジェクトでは、キューに配置されたメッセージを受信した順序で処理します。  
  
 `transformer` クラスでは、メッセージを 1 つのターゲットに送信します。 設定した場合、 `_PTarget` コンス トラクターのパラメーター `NULL`, を呼び出して、ターゲットを後で指定できる、 [concurrency::link_target](../Topic/source_block::link_target%20Method.md) メソッドです。  
  
 エージェント ライブラリに用意されている他のすべての非同期メッセージ ブロックの型とは異なり、`transformer` クラスでは異なる入力と出力の種類を操作できます。 データをある型から別の型に変換するこの機能により、`transformer` クラスは多くの同時実行ネットワークで重要なコンポーネントとなっています。 また、`transformer` オブジェクトの処理関数により詳細な並列機能を追加できます。  
  
### <a name="example"></a>例  
 次の例では、`transformer` クラスの使用方法の基本的な構造を示します。 この例では、`transformer` 値の出力を生成するために、`int` の各入力値に 0.33 を乗算する `double` オブジェクトを作成します。 その後、変換後の値を同じ `transformer` オブジェクトから受け取り、それらをコンソールに出力します。  
  
 [!code-cpp[concrt-transformer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_5.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
10.8914.5218.15  
```  
  
 使用する方法を示す完全な例については、 `transformer` を参照してください [方法: データ パイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="a-namechoicea-choice-class"></a><a name="choice"></a> choice クラス  
  [Concurrency::choice](../../parallel/concrt/reference/choice-class.md) クラスは、一連のソースから最初の使用可能なメッセージを選択します。  `choice` クラスは、データ フロー機構ではなく制御フロー機構を表します (トピック [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) データ フローと制御フローの違いについて説明します)。  
  
 choice オブジェクトからの読み取りは、`WaitForMultipleObjects` パラメーターが `bWaitAll` に設定されている場合の Windows API 関数 `FALSE` の呼び出しに似ています。 ただし、`choice` クラスでは、外部同期オブジェクトではなく、イベント自体にデータをバインドします。  
  
 通常、使用して、 `choice` と共に、 [concurrency::receive](../Topic/receive%20Function.md) 関数をアプリケーションで制御フローを進めます。 さまざまな型のメッセージ バッファーの中から選択する必要がある場合は、`choice` クラスを使用します。 同じ型のメッセージ バッファーの中から選択する必要がある場合は、`single_assignment` クラスを使用します。  
  
 ソースを `choice` オブジェクトにリンクさせる順序によって選択するメッセージを決定できるため、その順序は重要です。 たとえば、既にメッセージが格納されている複数のメッセージ バッファーを `choice` オブジェクトにリンクさせるとします。 `choice` オブジェクトによって、リンク先の最初のソースからメッセージが選択されます。 すべてのソースをリンクさせると、`choice` オブジェクトでは各ソースがメッセージを受信した順序を保持します。  
  
### <a name="example"></a>例  
 次の例では、`choice` クラスの使用方法の基本的な構造を示します。 この例では、 [concurrency::make_choice](../Topic/make_choice%20Function.md) を作成する関数、 `choice` 3 つのメッセージ ブロックを選択するオブジェクト。 次に、さまざまなフィボナッチ数列を計算し、それぞれの結果を別個のメッセージ ブロックに格納します。 その後、最初に終了した操作に基づくメッセージをコンソールに出力します。  
  
 [!code-cpp[concrt-choice-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_6.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
```Output  
fib35 received its value first. Result = 9227465  
```  
  
 35 を計算するタスク<sup>th</sup> フィボナッチ数は最初に終了する保証されませんが、この例の出力が変わることができます。  
  
 この例では、 [concurrency::parallel_invoke](../Topic/parallel_invoke%20Function.md) フィボナッチ数列を並列に計算するアルゴリズムです。 詳細については `parallel_invoke`, を参照してください [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)します。  
  
 使用する方法を示す完全な例については、 `choice` を参照してください [方法: 完了したタスクの間での選択](../../parallel/concrt/how-to-select-among-completed-tasks.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namejoina-join-and-multitypejoin-classes"></a><a name="join"></a> join クラスと multitype_join クラス  
  [Concurrency::join](../Topic/join%20Class.md) と [concurrency::multitype_join](../../parallel/concrt/reference/multitype-join-class.md) クラスを使用して、メッセージを受信する、一連のソースの各メンバーのまで待機できます。 `join` クラスでは、共通のメッセージ型を持つソース オブジェクトを処理します。 `multitype_join` クラスでは、異なるメッセージ型を持つことができるソース オブジェクトを処理します。  
  
 `join` オブジェクトまたは `multitype_join` オブジェクトからの読み取りは、`WaitForMultipleObjects` パラメーターが `bWaitAll` に設定されている場合の Windows API 関数 `TRUE` の呼び出しに似ています。 ただし、`choice` オブジェクトと同様に、`join` オブジェクトおよび `multitype_join` オブジェクトでは、外部同期オブジェクトではなく、イベント自体にデータをバインドするイベント機構を使用します。  
  
 読み取り、 `join` オブジェクトを生成、std::[ベクトル](../../standard-library/vector-class.md) オブジェクトです。 読み取り、 `multitype_join` オブジェクトを生成、std::[組](../../standard-library/tuple-class.md) オブジェクトです。 対応するソース バッファーと同じ順序でこれらのオブジェクトに出現する要素は、`join` オブジェクトまたは `multitype_join` オブジェクトにリンクされます。 ソース バッファーを `join` オブジェクトまたは `multitype_join` オブジェクトにリンクする順序は、結果の `vector` オブジェクトまたは `tuple` オブジェクトの要素の順序に関連するため、既存のソース バッファーを結合からリンク解除しないことをお勧めします。 そのようにすると、未定義の動作が発生する可能性があります。  
  
### <a name="greedy-versus-non-greedy-joins"></a>最長一致の結合と最短一致の結合  
 `join` クラスおよび `multitype_join` クラスでは、最長一致の結合と最短一致の結合の概念をサポートしています。 A *最長一致の結合* すべてのメッセージが使用可能になるまで、メッセージが公開されたらすぐに、各ソースからメッセージを受け入れます。 A *、最短一致の結合* 2 つのフェーズでメッセージを受信します。 まず、各ソースからメッセージが提供されるまで待機します。 次に、すべてのソースのメッセージが使用可能になったら、各メッセージの予約を試みます。 各メッセージを予約できる場合、すべてのメッセージを処理し、ターゲットに伝達します。 それ以外の場合、メッセージの予約を解除し (取り消し)、再び各ソースがメッセージを受信するまで待機します。  
  
 最長一致の結合はメッセージを即座に受け入れるため、最短一致の結合よりもパフォーマンスが優れています。 ただし、最長一致の結合では、デッドロックが発生する可能性がまれにあります。 1 つ以上の共有されたソース オブジェクトを含む複数の結合がある場合は、最短一致の結合を使用します。  
  
### <a name="example"></a>例  
 次の例では、`join` クラスの使用方法の基本的な構造を示します。 この例では、 [concurrency::make_join](../Topic/make_join%20Function.md) を作成する関数、 `join` を 3 から受け取る `single_assignment` オブジェクトです。 この例では、さまざまなフィボナッチ数列を計算し、それぞれの結果を別個の `single_assignment` オブジェクトに格納します。その後、`join` オブジェクトが保持している各結果をコンソールに出力します。 この例は `choice` クラスの例に似ています。ただし、`join` クラスでは、すべてのソース メッセージ ブロックがメッセージを受信するまで待機します。  
  
 [!code-cpp[concrt-join-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_7.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
fib35 = 9227465fib37 = 24157817half_of_fib42 = 1.33957e+008  
```  
  
 この例では、 [concurrency::parallel_invoke](../Topic/parallel_invoke%20Function.md) フィボナッチ数列を並列に計算するアルゴリズムです。 詳細については `parallel_invoke`, を参照してください [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)します。  
  
 使用する方法を示す完全な例については、 `join` を参照してください [方法: 完了したタスクの間での選択](../../parallel/concrt/how-to-select-among-completed-tasks.md) と [チュートリアル: join デッドロックの防止を使用した](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-nametimera-timer-class"></a><a name="timer"></a> timer クラス  
 同時実行性::[timer クラス](../../parallel/concrt/reference/timer-class.md) 、メッセージ ソースとして動作します。 `timer` オブジェクトでは、指定された時間が経過するとメッセージをターゲットに送信します。 `timer` クラスは、メッセージの送信を遅延させる必要がある場合や、定期的にメッセージを送信する場合に便利です。  
  
 `timer` クラスでは、メッセージを 1 つのターゲットにのみ送信します。 設定した場合、 `_PTarget` コンス トラクターのパラメーター `NULL`, を呼び出して、ターゲットを後で指定できる、 [concurrency::ISource::link_target](../Topic/source_block::link_target%20Method.md) メソッドです。  
  
 `timer` オブジェクトには、繰り返しと非繰り返しがあります。 繰り返しタイマーを作成するには、コンストラクターを呼び出すときに `true` パラメーターに `_Repeating` を渡します。 また、非繰り返しタイマーを作成するには、`false` パラメーターに `_Repeating` を渡します。 タイマーが繰り返しの場合、一定の間隔で同じメッセージをターゲットに送信します。  
  
 エージェント ライブラリによって、開始されていない状態の `timer` オブジェクトが作成されます。 タイマー オブジェクトを最初に呼び出す、 [::start](../Topic/timer::start%20Method.md) メソッドです。 停止する、 `timer` オブジェクトを呼び出し、オブジェクトの破棄、 [concurrency::timer::stop](../Topic/timer::stop%20Method.md) メソッドです。 繰り返しタイマーを一時停止を呼び出して、 [concurrency::timer::pause](../Topic/timer::pause%20Method.md) メソッドです。  
  
### <a name="example"></a>例  
 次の例では、`timer` クラスの使用方法の基本的な構造を示します。 この例では、`timer` オブジェクトと `call` オブジェクトを使用して、時間のかかる操作の進行状況を報告します。  
  
 [!code-cpp[concrt-timer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_8.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
```Output  
Computing fib(42)..................................................result is 267914296  
```  
  
 使用する方法を示す完全な例については、 `timer` を参照してください [方法: メッセージを定期的に送信する](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="a-namefilteringa-message-filtering"></a><a name="filtering"></a> メッセージのフィルター処理  
 メッセージ ブロック オブジェクトを作成するときは、指定、 *filter 関数* メッセージ ブロックを受け入れるか、メッセージを拒否するかどうかを決定します。 フィルター関数は、メッセージ ブロックが特定の値のみを受信するようにする便利な方法です。  
  
 次の例では、フィルター関数を使用して偶数のみを受け入れる `unbounded_buffer` オブジェクトを作成する方法を示します。 `unbounded_buffer` オブジェクトは奇数を拒否するため、奇数はターゲット ブロックに伝達されません。  
  
 [!code-cpp[concrt-filter-function#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_9.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
0 2 4 6 8  
```  
  
 ラムダ関数、関数ポインター、または関数オブジェクトをフィルター関数として使用できます。 各フィルター関数の形式は次のいずれかになります。  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 データの不必要なコピーをなくすには、値で伝達される集約型を扱うときに 2 番目の形式を使用します。  
  
 メッセージ フィルターのサポート、 *データフロー* プログラミング モデルにおいて、データを受信したときに、コンポーネント計算を実行します。 メッセージ パッシング ネットワーク内のデータのフローを制御するフィルター関数を使用する例については、次を参照してください。 [方法: メッセージ ブロック フィルターを使用して](../../parallel/concrt/how-to-use-a-message-block-filter.md), 、[チュートリアル: データフロー エージェントの作成](../Topic/Walkthrough:%20Creating%20a%20Dataflow%20Agent.md), 、および [チュートリアル: イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namereservationa-message-reservation"></a><a name="reservation"></a> メッセージの予約  
 *メッセージの予約* 、メッセージ ブロックに後で使用するためにメッセージを予約するようにします。 通常、メッセージの予約を直接使用することはありません。 ただし、メッセージの予約について理解しておくと、定義済みのいくつかのメッセージ ブロックの型の動作を理解しやすくなります。  
  
 最短一致の結合と最長一致の結合について考えてみてください。 どちらの場合も、メッセージの予約によって、後で使用できるようにメッセージを予約します。 前に述べたとおり、最短一致の結合では、2 つの段階でメッセージを受信します。 最初の段階で、最短一致の `join` オブジェクトは各ソースがメッセージを受信するまで待機します。 次に、各メッセージの予約を試みます。 各メッセージを予約できる場合、すべてのメッセージを処理し、ターゲットに伝達します。 それ以外の場合、メッセージの予約を解除し (取り消し)、再び各ソースがメッセージを受信するまで待機します。  
  
 最長一致の結合でも、複数のソースから入力メッセージを読み取ります。この場合、各ソースからメッセージを受信するのを待っている間、メッセージの予約を使用して追加のメッセージを読み取ります。 たとえば、メッセージ ブロック `A` および `B` からメッセージを受信する最長一致の結合を考えてみます。 B から 2 つのメッセージを受信し、`A` からはまだメッセージを受信していない場合、最長一致の結合は、`B` からの 2 番目のメッセージに対応する一意のメッセージ識別子を保存します。 `A` からメッセージを受信し、これらのメッセージを伝達した後、保存済みのメッセージ識別子を使用して、`B` からの 2 番目のメッセージがまだ有効かどうかを確認します。  
  
 独自のカスタム メッセージ ブロックの型を実装する場合は、メッセージの予約を使用できます。 カスタム メッセージ ブロックの型を作成する方法の例は、次を参照してください。 [チュートリアル: カスタム メッセージ ブロックの作成](../Topic/Walkthrough:%20Creating%20a%20Custom%20Message%20Block.md)します。  
  
 [[トップ](#top)]  
  
## <a name="see-also"></a>関連項目  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)

