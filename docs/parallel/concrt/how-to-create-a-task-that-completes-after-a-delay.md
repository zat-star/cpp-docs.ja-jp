---
title: "方法: 遅延後に完了するタスクを作成する | Microsoft Docs"
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
  - "task_completion_event クラスの例"
  - "例 [C++]、遅延の後に完了するタスクを作成します。"
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 方法: 遅延後に完了するタスクを作成する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

使用する方法を示します、 [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md), 、[concurrency::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md), 、[concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md), 、[concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), 、"concurrency::timer"と [concurrency::call](../../parallel/concrt/reference/call-class.md) 、遅延後に完了するタスクを作成するクラス。 このメソッドを使用する場合がありますのデータのポーリングのタイムアウトを導入、あらかじめ決められた時間では、ユーザー入力の処理を遅延に表示され、ループをビルドします。  
  
## <a name="example"></a>例  
 `complete_after` 関数および `cancel_after_timeout` 関数の例を次に示します。  `complete_after` 関数を作成、 `task` オブジェクトを指定した遅延後に完了します。 使用して、 `timer` オブジェクトと `call` を設定するオブジェクト、 `task_completion_event` 経過すると、指定したオブジェクト。 使用して、 `task_completion_event` クラス、スレッドの後に完了するタスクを定義することや、別のタスクは使用可能な値を示します。 イベントが設定されている場合は、リスナー タスクが完了し、その継続を実行するようにスケジュールします。  
  
> [!TIP]
>  詳細については、 `timer` と `call` 非同期エージェント ライブラリの一部のクラスを参照してください [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
  `cancel_after_timeout` 関数に基づき、 `complete_after` 関数を指定したタイムアウト時間の前にそのタスクが完了しない場合は、タスクを取り消します。  `cancel_after_timeout` 関数は 2 つのタスクを作成します。 最初のタスクの成功を示すし、指定されたタスクの完了後に完了2 番目のタスクは、エラーを示し、指定したタイムアウト後に完了します。  `cancel_after_timeout` 関数が成功または失敗のタスクが完了したときに実行される継続タスクを作成します。 エラー タスクには、1 つ目が終了すると、継続は、全体的なタスクをキャンセル トークン ソースをキャンセルします。  
  
 [!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/CPP/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]  
  
## <a name="example"></a>例  
 次の例は、[0, 100000] の範囲に含まれる素数の数を計算複数回です。 制限時間内に完了しないと、操作が失敗します。  `count_primes` 関数を使用する方法を示しています、 `cancel_after_timeout` 関数です。 特定の範囲内の素数の数をカウントし、指定された時間内にタスクが完了しない場合は失敗します。  `wmain` 関数呼び出し、 `count_primes` 複数回に機能します。 毎回制限時間は半分です。 プログラムの完了後、現在の時間制限内で操作が完了しません。  
  
 [!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/CPP/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]  
  
 遅延後にタスクをキャンセルするこの手法を使用すると、全体的なタスクが取り消された後、まだ開始していないタスクは開始されません。 ただし、これがキャンセルに応答する適切なタイミングで実行時間の長いタスクのため重要です。 この例では、 `count_primes` メソッドの呼び出し、 [concurrency::is_task_cancellation_requested](../../misc/is-task-cancellation-requested-function.md) と `cancel_current_task` キャンセルに応答する機能です。 (代わりに、呼び出すことができます、 [concurrency::interruption_point](../Topic/interruption_point%20Function.md) 関数)。 タスクのキャンセルの詳細については、次を参照してください。 [キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)します。  
  
## <a name="example"></a>例  
 この例の完全なコードを次に示します。  
  
 [!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/CPP/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コードをコンパイルするコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付ける `task-delay.cpp` Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc タスク delay.cpp**  
  
## <a name="see-also"></a>関連項目  
 [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [task クラス (同時実行ランタイム)](../../parallel/concrt/reference/task-class-concurrency-runtime.md)   
 [cancellation_token_source クラス](../../parallel/concrt/reference/cancellation-token-source-class.md)   
 [cancellation_token クラス](../../parallel/concrt/reference/cancellation-token-class.md)   
 [task_completion_event クラス](../../parallel/concrt/reference/task-completion-event-class.md)   
 [is_task_cancellation_requested 関数](../../misc/is-task-cancellation-requested-function.md)   
 [cancel_current_task 関数](../Topic/cancel_current_task%20Function.md)   
 [interruption_point 関数](../Topic/interruption_point%20Function.md)   
 [クラスを呼び出します。](../../parallel/concrt/reference/call-class.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)