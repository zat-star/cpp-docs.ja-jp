---
title: "コンテキスト | Microsoft Docs"
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
  - "コンテキスト [同時実行ランタイム]"
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# コンテキスト
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このドキュメントでは、同時実行ランタイムのコンテキストの役割について説明します。 スケジューラに関連付けられているスレッドと呼ばれる、 *実行コンテキスト*, 、または単 *コンテキスト*します。  [Concurrency::wait](../Topic/wait%20Function.md) 関数と、同時実行制御::[コンテキスト クラス](Context%20Class.md) を使用すると、コンテキストの動作を制御します。 使用して、 `wait` 関数を指定した時間、現在のコンテキストを中断します。 使用して、 `Context` クラスとコンテキストをブロックのブロックを解除/などや、現在のコンテキストをオーバーサブスク ライブしてする場合より詳細に制御する必要があります。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 タスク スケジューラにより、アプリケーションのパフォーマンスを微調整できますが、あるためにで開始することが勧め、 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) または [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) 同時実行ランタイムに慣れていない場合。  
  
## <a name="the-wait-function"></a>Wait 関数  
  [Concurrency::wait](../Topic/wait%20Function.md) 関数が協調的に指定したミリ秒数の現在のコンテキストの実行を譲歩します。 ランタイムでは、yield 時間を使用して、その他のタスクを実行します。 指定した時間が経過した後、ランタイム スケジュールの実行コンテキストを変更します。 したがって、 `wait` 関数は、現在のコンテキストに指定された値よりも長い中断可能性があります、 `milliseconds` パラメーター。  
  
 0 (ゼロ) を渡して、 `milliseconds` を他のすべてのアクティブなコンテキストで作業を実行する機会が与えられますまで、現在のコンテキストを中断するランタイムを発生させます。 これにより、他のすべてのアクティブなタスクに対してタスクを譲渡することができます。  
  
### <a name="example"></a>例  
 使用する例については、 `wait` 関数を現在のコンテキストを生成し、他のコンテキストを参照してください、実行を許可してしまう [方法: オーダーの実行に影響を使用してスケジュール グループ](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)します。  
  
## <a name="the-context-class"></a>Context クラス  
 同時実行性::[コンテキスト クラス](Context%20Class.md) 実行コンテキストのプログラミングの抽象化して 2 つの重要な機能を提供しています: 協調的ブロッキングのブロックを解除や、現在のコンテキストを譲渡など、現在のコンテキストをオーバーサブスク ライブして機能します。  
  
### <a name="cooperative-blocking"></a>協調ブロッキング  
 `Context` クラスを使用すると、現在の実行コンテキストをブロックまたは生成できます。 ブロックまたは生成は、リソースが使用できないため、現在のコンテキストを続行できない場合に便利です。  
  
  [Concurrency::Context::Block](../Topic/Context::Block%20Method.md) メソッドは、現在のコンテキストをブロックします。 ブロックされているコンテキストでは、ランタイムはその他のタスクを実行できるように、その処理リソースが得られます。  [Concurrency::Context::Unblock](../Topic/Context::Unblock%20Method.md) メソッド ブロックされているコンテキストのブロックを解除します。  `Context::Unblock` と呼ばれるものとは異なるコンテキストからメソッドを呼び出す必要があります `Context::Block`します。 ランタイムは、スロー [concurrency::context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) コンテキスト自体のブロックを解除しようとするとします。  
  
 協調的をブロックし、コンテキストのブロックを解除、通常呼び出す [concurrency::Context::CurrentContext](../Topic/Context::CurrentContext%20Method.md) へのポインターを取得する、 `Context` 結果を保存および現在のスレッドに関連付けられているオブジェクト。 次に呼び出し、 `Context::Block` 、現在のコンテキストをブロックするメソッドです。 その後を呼び出す `Context::Unblock` ブロックされているコンテキストのブロックを解除する別のコンテキストからです。  
  
 呼び出しの各ペアと一致する必要があります `Context::Block` と `Context::Unblock`です。 ランタイムは、スロー [concurrency::context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) ときに、 `Context::Block` または `Context::Unblock` メソッドが他のメソッドに一致する呼び出しがない連続して呼び出されます。 ただし、呼び出す必要はない `Context::Block` を呼び出す前に `Context::Unblock`します。 たとえば、1 つのコンテキストでは `Context::Unblock` 別のコンテキストの呼び出しの前に `Context::Block` の同一のコンテキストでは、そのコンテキストがブロックされていません。  
  
  [:Yield](../Topic/Context::Yield%20Method.md) 、ランタイムが他のタスクを実行して、コンテキストの実行スケジュールを変更できるように、メソッドが実行を譲歩します。 呼び出すと、 `Context::Block` メソッド、ランタイムが、コンテキストを再スケジュールします。  
  
#### <a name="example"></a>例  
 使用する例については、 `Context::Block`, 、`Context::Unblock`, 、および `Context::Yield` 協調セマフォ クラスを実装するメソッドを参照してください [方法: Context クラスを使用して協調セマフォを実装する](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)です。  
  
##### <a name="oversubscription"></a>オーバーサブスクリプション  
 既定のスケジューラには、利用可能なハードウェア スレッドが同じスレッド数が作成されます。 使用することができます *オーバー サブスクリプション* を特定のハードウェア スレッドの追加のスレッドを作成します。  
  
 負荷の高い計算操作は、オーバー サブスクリプション通常を拡張できませんオーバーヘッドが増えるため。 ただしの待機時間の時間が長いタスク、たとえば、ディスクやネットワーク接続からデータを読み取るオーバー サブスクリプション効率を向上できます全体的な一部のアプリケーションのです。  
  
> [!NOTE]
>  同時実行ランタイムによって作成されたスレッドからのみオーバー サブスクリプションを有効にします。 (メイン スレッドを含む)、ランタイムによって作成されていないスレッドから呼び出された場合は、オーバー サブスクリプションを指定しても効果はありません。  
  
 現在のコンテキストでオーバー サブスクリプションを有効にする、 [concurrency::Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md) メソッドを `_BeginOversubscription` パラメーターを設定する `true`です。 同時実行ランタイムによって作成されたスレッド上の使用率を有効にすると、追加の 1 つのスレッドを作成するランタイムが行われます。 オーバー サブスクリプション終了日を必要とするすべてのタスクの後に呼び出す `Context::Oversubscribe` で、 `_BeginOversubscription` パラメーターを設定する `false`です。  
  
 現在のコンテキストを複数回オーバー サブスクリプションを有効にすることができますが、有効にした同じ回数を無効する必要があります。 オーバー サブスクリプションも入れ子になんだことができます。つまり、オーバー サブスクリプションを使用する他のタスクによって作成されたタスクは、そのコンテキストをオーバーサブスク ライブできますもします。 ただし、入れ子になったタスクとその親の両方が、同じコンテキストへの最も外側の呼び出しだけに属している場合 `Context::Oversubscribe` 追加のスレッドを作成します。  
  
> [!NOTE]
>  ランタイムは、スロー [concurrency::invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) を有効にする前に、オーバー サブスクリプションが無効になっている場合。  
  
###### <a name="example"></a>例  
 オーバー サブスクリプションを使用して、ネットワーク接続からのデータの読み込みが原因で発生する待機時間を短縮する例を参照してください [方法: オフセットまでの待ち時間にオーバー サブスクリプションを使用して](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)します。  
  
## <a name="see-also"></a>関連項目  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [方法: スケジュール グループを使用して、実行の順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)   
 [方法: Context クラスを使用して協調セマフォを実装するには](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [方法: オーバー サブスクリプションを使用して、待機時間を短縮するには](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)

