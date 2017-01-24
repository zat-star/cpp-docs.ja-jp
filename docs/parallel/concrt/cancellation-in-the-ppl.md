---
title: "PPL における取り消し処理 | Microsoft Docs"
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
  - "キャンセル (並列アルゴリズムを) [同時実行ランタイム]"
  - "キャンセル (並列タスクを) [同時実行ランタイム]"
  - "キャンセル (PPL での)"
  - "並列アルゴリズム, キャンセル [同時実行ランタイム]"
  - "並列タスク, キャンセル [同時実行ランタイム]"
  - "並列処理ツリー [同時実行ランタイム]"
ms.assetid: baaef417-b2f9-470e-b8bd-9ed890725b35
caps.latest.revision: 31
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PPL における取り消し処理
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このドキュメントでは、並列パターン ライブラリ \(PPL: Parallel Patterns Library\) での取り消し処理の役割、並列処理を取り消す方法、および並列処理の取り消しを判定する方法について説明します。  
  
> [!NOTE]
>  ランタイムは例外処理を使用して取り消し処理を実装します。  これらの例外をコードでキャッチまたは処理しないでください。  さらに、タスクの関数本体では例外セーフなコードを作成することをお勧めします。  たとえば、*Resource Acquisition Is Initialization* \(RAII\) パターンを使用すると、例外がタスクの本体でスローされたときに、リソースを正しく処理することができます。  取り消し可能なタスクで RAII パターンを使用してリソースをクリーンアップする完全な例については、「[チュートリアル: ユーザー インターフェイス スレッドからの処理の除去](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)」を参照してください。  
  
## 主要なポイント  
  
-   取り消し処理は他の処理と連携して行われ、取り消し処理を要求するコードと取り消し処理に応答するタスクの間に連携が必要です。  
  
-   可能な場合は、キャンセル トークンを使用して処理を取り消します。  [concurrency::cancellation\_token](../../parallel/concrt/reference/cancellation-token-class.md) クラスで、キャンセル トークンを定義します。  
  
-   キャンセル トークンを使用する場合、[concurrency::cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md) メソッドを使用して取り消し処理を開始し、[concurrency::cancel\_current\_task](../Topic/cancel_current_task%20Function.md) 関数を使用して取り消し処理に応答します。  
  
-   取り消し処理はすぐに実行されません。  タスクまたはタスク グループが取り消される場合、新しい処理は開始されませんが、アクティブな処理は取り消し状態をチェックし、取り消し処理に応答する必要があります。  
  
-   値ベースの継続は、継続元タスクのキャンセル トークンを継承します。  タスク ベースの継続は、継続元タスクのトークンを継承しません。  
  
-   [concurrency::cancellation\_token::none](../Topic/cancellation_token::none%20Method.md) オブジェクトを受け取るコンストラクターまたは関数を呼び出し、その操作を取り消し可能にしない場合は、`cancellation_token` メソッドを使用します。  また、[concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) コンストラクターまたは [concurrency::create\_task](../Topic/create_task%20Function.md) 関数にキャンセル トークンを渡さない場合、そのタスクは取り消し可能になりません。  
  
##  <a name="top"></a> 目次  
  
-   [並列処理ツリー](#trees)  
  
-   [並列タスクの取り消し](#tasks)  
  
    -   [キャンセル トークンを使用して並列処理を取り消す](#tokens)  
  
    -   [cancel メソッドを使用した並列処理の取り消し](#cancel)  
  
    -   [例外を使用した並列処理の取り消し](#exceptions)  
  
-   [並列アルゴリズムの取り消し](#algorithms)  
  
-   [取り消し処理が適さないケース](#when)  
  
##  <a name="trees"></a> 並列処理ツリー  
 PPL は、細かく分類されたタスクおよび計算を管理するためにタスクとタスク グループを使用します。  タスク グループを入れ子にすることで、並列処理の*ツリー*を形成できます。  並列処理ツリーの図を次に示します。  この図では、`tg1` と `tg2` はタスク グループを表し、`t1`、`t2`、`t3`、`t4`、および `t5` はタスク グループによって実行される処理を表しています。  
  
 ![並列処理ツリー](../../parallel/concrt/media/parallelwork_trees.png "ParallelWork\_Trees")  
  
 前の図のツリーを作成するために必要なコード例を次に示します。  この例では、`tg1` と `tg2` が [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) オブジェクトで、`t1`、`t2`、`t3`、`t4`、および `t5` が [concurrency::task\_handle](../../parallel/concrt/reference/task-handle-class.md) オブジェクトです。  
  
 [!code-cpp[concrt-task-tree#1](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_1.cpp)]  
  
 また、同様の処理ツリーを作成するために [concurrency::task\_group](../Topic/task_group%20Class.md) クラスを使用できます。  [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) クラスでも、処理ツリーの概念をサポートしています。  ただし、`task` ツリーは依存ツリーです。  `task` ツリーでは、将来の処理は現在の処理の後に完了します。  タスク グループ ツリーでは、内部処理は外部処理の前に完了します。  タスクとタスク グループの違いの詳細については、「[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="tasks"></a> 並列タスクの取り消し  
 並列処理を取り消すには複数の方法があります。  推奨する方法は、キャンセル トークンを使用する方法です。  また、タスク グループでは、[concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md) メソッドと [concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md) メソッドをサポートしています。  最後の方法は、タスクの処理関数の本体で例外をスローする方法です。  どの方法を選択した場合でも、取り消し処理はすぐに実行されません。  タスクまたはタスク グループが取り消される場合、新しい処理は開始されませんが、アクティブな処理は取り消し状態をチェックし、取り消し処理に応答する必要があります。  
  
 並列タスクの取り消しの例については、「[チュートリアル: タスクおよび XML HTTP 要求を使用した接続](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)」、「[方法: キャンセル処理を使用して並列ループを中断する](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)」、および「[方法: 例外処理を使用して並列ループを中断する](../Topic/How%20to:%20Use%20Exception%20Handling%20to%20Break%20from%20a%20Parallel%20Loop.md)」を参照してください。  
  
###  <a name="tokens"></a> キャンセル トークンを使用して並列処理を取り消す  
 `task`、`task_group`、および `structured_task_group` の各クラスでは、キャンセル トークンを使用した取り消し処理をサポートしています。  PPL では、このために [concurrency::cancellation\_token\_source](../../parallel/concrt/reference/cancellation-token-source-class.md) クラスと [concurrency::cancellation\_token](../../parallel/concrt/reference/cancellation-token-class.md) クラスが定義されています。  作業を取り消すためにキャンセル トークンを使用すると、ランタイムはそのトークンをサブスクライブする新しい作業を開始しません。  既にアクティブである作業はそのキャンセル トークンを監視でき、可能な場合には停止できます。  
  
 取り消し処理を開始するには、[concurrency::cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md) メソッドを呼び出します。  次の方法で取り消し処理に応答します。  
  
-   `task` オブジェクトには、[concurrency::cancel\_current\_task](../Topic/cancel_current_task%20Function.md) 関数を使用します。  `cancel_current_task` が現在のタスクとすべての値ベースの継続を取り消します  \(タスクまたはその継続に関連付けられているキャンセル *トークン*は取り消しません\)。  
  
-   タスク グループと並列アルゴリズムの場合は、[concurrency::is\_current\_task\_group\_canceling](../Topic/is_current_task_group_canceling%20Function.md) 関数を使用して取り消し処理を検出し、この関数によって `true` が返される場合はできるだけ早くタスクの本体から戻ります  \(タスク グループから `cancel_current_task` を呼び出さないでください\)。  
  
 次の例では、タスク取り消し処理の最初の基本的なパターンを示しています。  タスクの本体は、ループ内の取り消し状態を適宜チェックします。  
  
 [!code-cpp[concrt-task-basic-cancellation#1](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_2.cpp)]  
  
 `cancel_current_task` 関数がスローします。したがって、現在のループまたは関数から明示的に戻る必要はありません。  
  
> [!TIP]
>  また、`cancel_current_task` の代わりに、[concurrency::interruption\_point](../Topic/interruption_point%20Function.md) 関数を呼び出すこともできます。  
  
 取り消し処理に応答するときは `cancel_current_task` を呼び出すことが重要です。この関数によって、タスクが取り消し状態に遷移します。  `cancel_current_task` を呼び出さずに早期に戻った場合、操作は完了状態に遷移し、すべての値ベースの継続が実行されます。  
  
> [!CAUTION]
>  コードから `task_canceled` をスローしないでください。  代わりに `cancel_current_task` を呼び出してください。  
  
 タスクが取り消し状態になると、[concurrency::task::get](../Topic/task::get%20Method.md) メソッドは [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md) をスローします  \(逆に、[concurrency::task::wait](../Topic/task::wait%20Method.md) は [task\_status::canceled](../Topic/task_group_status%20Enumeration.md) を返し、スローしません\)。 次の例では、タスク ベースの継続のこの動作を示します。  タスク ベースの継続は、その継続元タスクが取り消された場合でも必ず呼び出されます。  
  
 [!code-cpp[concrt-task-canceled#1](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_3.cpp)]  
  
 値ベースの継続は、明示的なトークンで作成された場合を除き、継続元タスクのトークンを継承するため、継続元タスクがまだ実行中の場合でも、すぐに取り消し状態になります。  したがって、取り消し後に継続元タスクによってスローされた例外は、継続タスクに反映されません。  取り消し処理によって、継続元タスクの状態は常にオーバーライドされます。  次の例は、前の例に似ていますが、値ベースの継続の動作を示しています。  
  
 [!code-cpp[concrt-task-canceled#2](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_4.cpp)]  
  
> [!CAUTION]
>  `task` コンストラクターまたは [concurrency::create\_task](../Topic/create_task%20Function.md) 関数にキャンセル トークンを渡さない場合、そのタスクは取り消し可能になりません。  また、入れ子のタスク \(別のタスクの本体で作成されたタスク\) のコンストラクターに同じキャンセル トークンを渡して、すべてのタスクを同時に取り消す必要があります。  
  
 キャンセル トークンが取り消されるときに任意のコードを実行できます。  たとえば、操作を取り消すためにユーザーがユーザー インターフェイスの **\[キャンセル\]** ボタンをクリックした場合、ユーザーが別の操作を開始するまでそのボタンを無効にすることができます。  次の例では、[concurrency::cancellation\_token::register\_callback](../Topic/cancellation_token::register_callback%20Method.md) メソッドを使用して、キャンセル トークンが取り消されるときに実行されるコールバック関数を登録する方法を示します。  
  
 [!code-cpp[concrt-task-cancellation-callback#1](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_5.cpp)]  
  
 「[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)」のドキュメントでは、値ベースの継続とタスク ベースの継続との違いについて説明しています。  継続タスクに `cancellation_token` オブジェクトを提供しない場合、継続はキャンセル トークンを継続元タスクから次のように継承します。  
  
-   値ベースの継続は、継続元タスクのキャンセル トークンを必ず継承します。  
  
-   タスク ベースの継続は、継続元タスクのキャンセル トークンを継承しません。  タスク ベースの継続を取り消し可能にする唯一の方法は、明示的にキャンセル トークンを渡すことです。  
  
 これらの動作は、違反になったタスク \(つまり、例外をスローするタスク\) の影響を受けません。  この場合、値ベースの継続は取り消され、タスク ベースの継続は取り消されません。  
  
> [!CAUTION]
>  別のタスクに作成されているタスク \(つまり、入れ子のタスク\) は、親タスクのキャンセル トークンを継承しません。  値ベースの継続のみ、継続元タスクのキャンセル トークンを継承します。  
  
> [!TIP]
>  [concurrency::cancellation\_token::none](../Topic/cancellation_token::none%20Method.md) オブジェクトを受け取るコンストラクターまたは関数を呼び出し、その操作を取り消し可能にしない場合は、`cancellation_token` メソッドを使用します。  
  
 また、`task_group` オブジェクトまたは `structured_task_group` オブジェクトのコンストラクターにキャンセル トークンを指定できます。  このとき重要な点は、子タスク グループがこのキャンセル トークンを継承することです。  [concurrency::run\_with\_cancellation\_token](../Topic/run_with_cancellation_token%20Function.md) を呼び出すときに実行される `parallel_for` 関数を使用して、この概念を示している例については、このドキュメントで後述する「[並列アルゴリズムの取り消し](#algorithms)」を参照してください。  
  
 \[[トップ](#top)\]  
  
#### キャンセル トークンとタスク構成  
 [concurrency::when\_all](../Topic/when_all%20Function.md) 関数と [concurrency::when\_any](../Topic/when_all%20Function.md) 関数は、共通のパターンを実装するために複数のタスクを構成するときに役立ちます。  このセクションでは、キャンセル トークンを使用した場合のこれらの関数の動作について説明します。  
  
 キャンセル トークンを `when_all` 関数または `when_any` 関数に指定すると、その関数は、そのキャンセル トークンが取り消されたとき、または参加タスクの 1 つが取り消し状態になるか例外をスローしたときにのみ取り消します。  
  
 `when_all` 関数にキャンセル トークンを指定していない場合、この関数は、操作全体を構成する各タスクからキャンセル トークンを継承します。  `when_all` から返されるタスクは、これらのトークンのいずれかが取り消され、1 つ以上の参加タスクがまだ開始されていないか実行中のときに取り消されます。  同様の動作は、タスクの 1 つが例外をスローしたときに発生します。`when_all` から返されるタスクは、その例外によってすぐに取り消されます。  
  
 ランタイムは、タスクが完了したときに `when_any` 関数から返されるタスクのキャンセル トークンを選択します。  完了状態になった参加タスクがなく、1 つまたは複数のタスクが例外をスローした場合、スローしたタスクの 1 つが `when_any` を完了するために選択され、そのトークンが最後のタスクのトークンとして選択されます。  複数のタスクが完了状態になった場合、`when_any` タスクから返されるタスクは、完了状態になります。  ランタイムは、他の実行中のタスクが後で完了する可能性がある場合でも、`when_any` から返されるタスクがすぐに取り消されないように、完了時にトークンが取り消されていない完了したタスクを選択しようとします。  
  
 \[[トップ](#top)\]  
  
###  <a name="cancel"></a> cancel メソッドを使用した並列処理の取り消し  
 [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md) メソッドおよび [concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md) メソッドは、タスク グループを取り消し状態に設定します。  `cancel` を呼び出すと、それ以降はタスク グループでタスクが開始されなくなります。  `cancel` メソッドは、複数の子タスクから呼び出すことができます。  タスクを取り消すと、[concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md) メソッドおよび [concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md) メソッドで [concurrency::canceled](../Topic/task_group_status%20Enumeration.md) が返されるようになります。  
  
 タスク グループが取り消されると、各子タスクからのランタイムの呼び出しによって*割り込みポイント*が発生する場合があります。このような場合、ランタイムは内部的な例外をスローおよびキャッチして、実行中のタスクを取り消します。  同時実行ランタイムでは、特定の割り込みポイントが定義されていません。割り込みポイントは、ランタイムに対する任意の呼び出しで発生します。  ランタイムは、取り消し処理を実行するために、自身がスローした例外を処理する必要があります。  このため、タスクの本体で不明な例外を処理しないでください。  
  
 子タスクが時間のかかる処理を実行しており、ランタイムの呼び出しを行わない場合、子タスクは定期的に取り消し状態をチェックして、適切なタイミングで終了する必要があります。  処理の取り消し状態を判定する方法の 1 つを次の例に示します。  タスク `t4` は、エラーの発生時に親タスク グループを取り消します。  タスク `t5` は、`structured_task_group::is_canceling` メソッドを定期的に呼び出して、取り消し状態をチェックします。  親タスク グループが取り消されると、タスク `t5` はメッセージを表示して終了します。  
  
 [!code-cpp[concrt-task-tree#6](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_6.cpp)]  
  
 この例では、タスク ループが 100 回繰り返されるたびに取り消し状態がチェックされます。  取り消し状態をチェックする頻度は、タスクで実行される処理の量と、取り消し処理にタスクがどの程度すばやく応答する必要があるのかによって決まります。  
  
 親タスク グループ オブジェクトにアクセスできない場合は、[concurrency::is\_current\_task\_group\_canceling](../Topic/is_current_task_group_canceling%20Function.md) 関数を呼び出して、親タスク グループが取り消されたかどうかを確認します。  
  
 `cancel` メソッドは、子タスクにのみ影響を及ぼします。  たとえば、並列処理ツリーの図のタスク グループ `tg1` を取り消すと、ツリー内のすべてのタスク \(`t1`、`t2`、`t3`、`t4`、および `t5`\) が取り消されます。  入れ子になったタスク グループ `tg2` を取り消すと、タスク `t4` および `t5` のみ影響を受けます。  
  
 `cancel` メソッドを呼び出すと、子タスク グループもすべて取り消されます。  しかし、取り消し処理は、並列処理ツリーにおけるタスク グループの親には影響しません。  以降の例では、並列処理ツリーの図に基づいてこのことを示します。  
  
 最初の例では、タスク グループ `t4` の子であるタスク `tg2` の処理関数を作成します。  この処理関数は、関数 `work` をループ内で呼び出します。  `work` の呼び出しが失敗すると、タスクは親タスク グループを取り消します。  これにより、タスク グループ `tg2` が取り消された状態になりますが、タスク グループ `tg1` は取り消されません。  
  
 [!code-cpp[concrt-task-tree#2](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_7.cpp)]  
  
 次の例は、最初の例と似ていますが、タスクがタスク グループ `tg1` を取り消す点が異なっています。  これにより、ツリー内のすべてのタスク \(`t1`、`t2`、`t3`、`t4`、および `t5`\) が影響を受けます。  
  
 [!code-cpp[concrt-task-tree#3](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_8.cpp)]  
  
 `structured_task_group` クラスはスレッドセーフではありません。  したがって、子タスクが親 `structured_task_group` オブジェクトのメソッドを呼び出すと、未定義の動作が実行されます。  ただし、`structured_task_group::cancel` メソッドと [concurrency::structured\_task\_group::is\_canceling](../Topic/structured_task_group::is_canceling%20Method.md) メソッドには、この規則が適用されません。  子タスクがこれらのメソッドを呼び出すことで、親タスク グループを取り消したり、取り消し状態をチェックしたりできます。  
  
> [!CAUTION]
>  `task` オブジェクトの子として実行するタスク グループによって実行される処理を取り消すためにキャンセル トークンを使用できますが、タスク グループで実行する `task_group::cancel` オブジェクトを取り消すために `structured_task_group::cancel` メソッドまたは `task` メソッドは使用できません。  
  
 \[[トップ](#top)\]  
  
###  <a name="exceptions"></a> 例外を使用した並列処理の取り消し  
 並列処理ツリーを取り消す場合は、例外処理を行うよりもキャンセル トークンと `cancel` メソッドを使用する方が効率的です。  キャンセル トークンと `cancel` メソッドは、タスクとすべての子タスクを上位から順に取り消します。  反対に、例外処理では下位から順に処理されるため、例外が上位へ移動するたびに、子タスク グループを個別に取り消す必要があります。  「[例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)」では、同時実行ランタイムが例外を使用してエラーを通知するしくみについて説明しています。  しかし、すべての例外がエラーの発生を示す訳ではありません。  たとえば、検索アルゴリズムでは、結果の検出時に関連付けられたタスクが取り消される場合があります。  しかし、前述したように、並列処理の取り消しを行う場合、例外処理は `cancel` メソッドを使用するよりも効率の点で劣ります。  
  
> [!CAUTION]
>  必要なときにだけを並列処理を取り消すために例外を使用することをお勧めします。  キャンセル トークンとタスク グループの `cancel` メソッドの方が効率的で、エラーが発生する可能性も低くなります。  
  
 タスク グループに渡す処理関数の本体で例外をスローすると、ランタイムはその例外を保存して、タスク グループの終了を待機するコンテキストにその例外をマーシャリングします。  `cancel` メソッドの場合と同様に、ランタイムはまだ開始されていないタスクを破棄し、新しいタスクを受け付けません。  
  
 次の 3 つ目の例は、2 つ目の例と似ていますが、タスク `t4` が例外をスローすることでタスク グループ `tg2` を取り消している点が異なります。  この例では、`try`\-`catch` ブロックを使用して、タスク グループ `tg2` が子タスクの終了を待機しているときに取り消し状態をチェックします。  最初の例と同様に、これによってタスク グループ `tg2` が取り消された状態になりますが、タスク グループ `tg1` は取り消されません。  
  
 [!code-cpp[concrt-task-tree#4](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_9.cpp)]  
  
 次の 4 つ目の例では、例外処理を使用して処理ツリー全体を取り消します。  この例では、タスク グループ `tg1` が子タスクの終了を待機しているときではなく、タスク グループ `tg2` が子タスクの終了を待機しているときに、例外をキャッチします。  2 番目の例と同様に、これによってツリー内の 2 つのタスク グループ `tg1` および `tg2` の両方が取り消された状態になります。  
  
 [!code-cpp[concrt-task-tree#5](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_10.cpp)]  
  
 `task_group::wait` メソッドと `structured_task_group::wait` メソッドは、子タスクが例外をスローしたときに実行されるため、これらのメソッドから戻り値を受け取ることはありません。  
  
 \[[トップ](#top)\]  
  
##  <a name="algorithms"></a> 並列アルゴリズムの取り消し  
 PPL の並列アルゴリズム \(`parallel_for` など\) は、タスク グループを基準として構築されています。  このため、これまで説明した方法のうちの多くを使用して、並列アルゴリズムを取り消すことができます。  
  
 以降の例では、並列アルゴリズムを取り消すためのいくつかの方法を示します。  
  
 `run_with_cancellation_token` 関数を使用して `parallel_for` アルゴリズムを呼び出す例を次に示します。  `run_with_cancellation_token` 関数は、引数としてキャンセル トークンを受け取り、指定された処理関数を同期的に呼び出します。  並列アルゴリズムはタスクに基づいて構築されるため、親タスクのキャンセル トークンを継承します。  したがって、`parallel_for` は取り消し処理に応答できます。  
  
 [!code-cpp[concrt-cancel-parallel-for#1](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_11.cpp)]  
  
 [concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md) メソッドを使用して `parallel_for` アルゴリズムを呼び出す例を次に示します。  `structured_task_group::run_and_wait` メソッドは、指定されたタスクの終了を待機します。  `structured_task_group` オブジェクトによって、処理関数でタスクを取り消すことができるようになります。  
  
 [!code-cpp[concrt-task-tree#7](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_12.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **The task group status is: canceled.** 例外処理を使用して `parallel_for` ループを取り消す例を次に示します。  ランタイムは、例外を呼び出し元のコンテキストにマーシャリングします。  
  
 [!code-cpp[concrt-task-tree#9](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_13.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **Caught 50** ブール型のフラグを使用して `parallel_for` ループに取り消し処理を組み込む例を次に示します。  この例では、`cancel` メソッドや例外処理を使用して一連のタスク全体を取り消している訳ではないため、すべてのタスクが実行されます。  したがって、この方法では、取り消しメソッドを使用するよりも多くの計算オーバーヘッドが発生する場合があります。  
  
 [!code-cpp[concrt-task-tree#8](../../parallel/concrt/codesnippet/CPP/cancellation-in-the-ppl_14.cpp)]  
  
 どの取り消し方法にも、他の方法にはない利点があります。  特定のニーズに合った方法を採用してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="when"></a> 取り消し処理が適さないケース  
 取り消し処理は、関連するタスク グループの各メンバーが適時に終了できる場合には適しています。  しかし、取り消し処理がアプリケーションに適さないケースもあります。  たとえば、タスクの取り消しは他の処理と連携して行われるため、個別のタスクがブロックされている場合は、一連のタスク全体を取り消すことができなくなります。  また、あるタスクがまだ開始されていないが、他の実行中のタスクのブロックを解除する場合、タスク グループが取り消されると、そのタスクは開始されません。  これにより、アプリケーションでデッドロックが発生する場合があります。  また、取り消し対象のタスクの子タスクで重要な操作 \(リソースの解放など\) が実行されるような状況でも、取り消し処理の使用はふさわしくありません。  親タスクを取り消すと一連のタスクがすべて取り消されるため、その操作は実行されなくなります。  この点を示す例については、「並列パターン ライブラリに関するベスト プラクティス」の「[取り消し処理および例外処理がオブジェクトの破棄に及ぼす影響について](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction)」のセクションを参照してください。  
  
 \[[トップ](#top)\]  
  
## 関連トピック  
  
|タイトル|説明|  
|----------|--------|  
|[方法: キャンセル処理を使用して並列ループを中断する](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)|取り消し処理を使用して並列検索アルゴリズムを実装する方法について説明します。|  
|[方法: 例外処理を使用して並列ループを中断する](../Topic/How%20to:%20Use%20Exception%20Handling%20to%20Break%20from%20a%20Parallel%20Loop.md)|`task_group` クラスを使用して基本的なツリー構造の検索アルゴリズムを作成する方法を示します。|  
|[例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)|タスク グループ、軽量タスク、および非同期エージェントによってスローされた例外をランタイムが処理するしくみ、およびアプリケーション内で例外に応答する方法を説明します。|  
|[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|タスクとタスク グループの関係のほか、アプリケーションで非構造化タスクと構造化タスクを使用する方法について説明します。|  
|[並列アルゴリズム](../Topic/Parallel%20Algorithms.md)|データのコレクションに対して同時処理を実行する並列アルゴリズムについて説明します。|  
|[並列パターン ライブラリ \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md)|並列パターン ライブラリの概要を説明します。|  
  
## 参照  
 [task クラス \(同時実行ランタイム\)](../../parallel/concrt/reference/task-class-concurrency-runtime.md)  
  
 [cancellation\_token\_source クラス](../../parallel/concrt/reference/cancellation-token-source-class.md)  
  
 [cancellation\_token クラス](../../parallel/concrt/reference/cancellation-token-class.md)  
  
 [task\_group クラス](../Topic/task_group%20Class.md)  
  
 [structured\_task\_group クラス](../../parallel/concrt/reference/structured-task-group-class.md)  
  
 [parallel\_for 関数](../Topic/parallel_for%20Function.md)