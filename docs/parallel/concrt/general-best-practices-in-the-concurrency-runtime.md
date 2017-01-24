---
title: "同時実行ランタイムに関する全般的なベスト プラクティス | Microsoft Docs"
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
  - "同時実行ランタイム、全般的なベスト プラクティス"
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
caps.latest.revision: 16
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 同時実行ランタイムに関する全般的なベスト プラクティス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、同時実行ランタイムの複数の領域に適用されるベスト プラクティスについて説明します。  
  
##  <a name="top"></a> セクション  
 このドキュメントは、次のセクションで構成されています。  
  
-   [可能であれば協調的同期コンストラクトを使用する](#synchronization)  
  
-   [時間のかかるタスクを譲渡なしで実行するのは避ける](#yield)  
  
-   [オーバーサブスクリプションを使用してブロッキング操作や待機時間の長い操作の影響を軽減する](#oversubscription)  
  
-   [可能であれば同時実行メモリ管理関数を使用する](#memory)  
  
-   [RAII を使用して同時実行オブジェクトの有効期間を管理する](#raii)  
  
-   [グローバル スコープでは同時実行オブジェクトを作成しない](#global-scope)  
  
-   [共有データ セグメントでは同時実行オブジェクトを使用しない](#shared-data)  
  
##  <a name="synchronization"></a> 可能であれば協調的同期コンストラクトを使用する  
 同時実行ランタイムには、外部同期オブジェクトを必要としない同時実行セーフのコンストラクトが多数用意されています。  たとえば、[concurrency::concurrent\_vector](../../parallel/concrt/reference/concurrent-vector-class.md) クラスを使用すると、同時実行セーフの追加操作と要素アクセス操作を実行できます。  ただし、リソースへの排他アクセスを必要とする場合に備えて、[concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) クラス、[concurrency::reader\_writer\_lock](../Topic/reader_writer_lock%20Class.md) クラス、および [concurrency::event](../Topic/event%20Class.md) クラスも用意されています。  これらの型は協調的に動作するため、タスク スケジューラは、最初のタスクがデータを待っている間、処理リソースを別のコンテキストに再割り当てすることができます。  可能であれば、協調的に動作しない他の同期機構 \(Windows API に用意されている同期機構など\) の代わりに、これらの同期型を使用してください。  これらの同期型の詳細およびコード例については、「[同期データ構造](../Topic/Synchronization%20Data%20Structures.md)」および「[同期データ構造と Windows API の比較](../Topic/Comparing%20Synchronization%20Data%20Structures%20to%20the%20Windows%20API.md)」を参照してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="yield"></a> 時間のかかるタスクを譲渡なしで実行するのは避ける  
 タスク スケジューラは協調的に動作するため、タスク間で公平性は保たれません。  したがって、1 つのタスクが原因で他のタスクを開始できなくなることがあります。  このような状況は許容される場合もありますが、デッドロックやスタベーションを引き起こす場合もあります。  
  
 次の例では、割り当てられている処理リソースの数を超えるタスクを実行します。  1 つ目のタスクはタスク スケジューラに譲渡しないため、そのタスクが終了するまで 2 つ目のタスクは開始されません。  
  
 [!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
 1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000  
  
 いくつかの方法を使用して、2 つのタスク間の協調を有効にすることができます。  1 つは、長時間実行されるタスクの中でタスク スケジューラに譲渡する時間を不定期に設けることです。  次の例では、[concurrency::Context::Yield](../Topic/Context::Yield%20Method.md) メソッドを呼び出すように `task` 関数を変更し、このメソッドによってタスク スケジューラに実行を譲渡して別のタスクを実行できるようにします。  
  
 [!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_2.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **1: 250000000**  
**2: 250000000**  
**1: 500000000**  
**2: 500000000**  
**1: 750000000**  
**2: 750000000**  
**1: 1000000000**  
**2: 1000000000** `Context::Yield` メソッドが譲渡するのは、現在のスレッドが属しているスケジューラ上の別のアクティブ スレッド、軽量タスク、または別のオペレーティング システム スレッドのみです。  このメソッドは、[concurrency::task\_group](../Topic/task_group%20Class.md) オブジェクトまたは [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) オブジェクトで実行されるようにスケジュールされ、まだ開始されていない処理には譲渡しません。  
  
 他の方法を使用して、長時間実行されるタスク間の協調を有効にすることもできます。  大きなタスクを小さなサブタスクに分割できます。  また、時間のかかるタスクの中でオーバーサブスクリプションを有効にすることもできます。  オーバーサブスクリプションを使用すると、使用可能なハードウェア スレッドよりも多くのスレッドを作成できます。  オーバーサブスクリプションは、長時間実行されるタスクの中で非常に長い待機時間 \(ディスクやネットワーク接続からのデータの読み取りなど\) が発生するような場合に特に役立ちます。  軽量タスクおよびオーバーサブスクリプションの詳細については、「[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)」を参照してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="oversubscription"></a> オーバーサブスクリプションを使用してブロッキング操作や待機時間の長い操作の影響を軽減する  
 同時実行ランタイムには、タスク間での協調的なブロッキングや譲渡を可能にする同期プリミティブ \([concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) など\) が用意されています。  最初のタスクが協調的なブロッキングや譲渡を行った場合、タスク スケジューラは、そのタスクがデータを待っている間、処理リソースを別のコンテキストに再割り当てすることができます。  
  
 同時実行ランタイムに用意されている協調的ブロッキング機構を使用できない場合もあります。  たとえば、使用する外部ライブラリによっては、別の同期機構が使用されることがあります。  別の例としては、Windows API `ReadFile` 関数を使用してネットワーク接続からデータを読み取る場合など、非常に長い待機時間が発生するような操作を実行する場合です。  このような場合、オーバーサブスクリプションを使用して、該当するタスクがアイドル状態のときに他のタスクが実行されるようにすることができます。  オーバーサブスクリプションを使用すると、使用可能なハードウェア スレッドよりも多くのスレッドを作成できます。  
  
 次の関数 `download` について考えます。この関数では、特定の URL にあるファイルをダウンロードします。  この例では、[concurrency::Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md) メソッドを使用して、アクティブ スレッドの数を一時的に増やします。  
  
 [!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_3.cpp)]  
  
 `GetHttpFile` 関数は潜在的な操作を実行するため、オーバーサブスクリプションを使用することで、現在のタスクがデータを待っている間、他のタスクを実行できるようになります。  この例の完全なバージョンについては、「[方法: オーバーサブスクリプションを使用して待機時間を短縮する](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)」を参照してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="memory"></a> 可能であれば同時実行メモリ管理関数を使用する  
 有効期間が比較的短い小さなオブジェクトを頻繁に割り当てるような粒度の細かいタスクを実行する場合、メモリ管理関数 [concurrency::Alloc](../Topic/Alloc%20Function.md) および [concurrency::Free](../Topic/Free%20Function.md) を使用します。  同時実行ランタイムでは、実行中のスレッドごとに別個のメモリ キャッシュが保持されます。  `Alloc` 関数と `Free` 関数は、ロックやメモリ バリアを使用することなく、これらのキャッシュからメモリの割り当てと解放を行います。  
  
 これらのメモリ管理関数の詳細については、「[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)」を参照してください。  これらの関数の使用例については、「[方法: Alloc および Free を使用してメモリ パフォーマンスを改善する](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)」を参照してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="raii"></a> RAII を使用して同時実行オブジェクトの有効期間を管理する  
 同時実行ランタイムでは、例外処理を使用して、取り消し処理などの機能を実装します。  したがって、ランタイムを呼び出す場合や、ランタイムを呼び出す別のライブラリを呼び出す場合は、例外セーフなコードを記述してください。  
  
 *Resource Acquisition Is Initialization* \(RAII\) パターンは、特定のスコープで同時実行オブジェクトの有効期間を安全に管理できる方法の 1 つです。  RAII パターンでは、データ構造はスタック上に割り当てられます。  データ構造は、作成されたときにリソースを初期化または取得し、破棄されたときにそのリソースを破棄または解放します。  RAII パターンでは、外側のスコープが終了する前に、常にデストラクターが呼び出されます。  このパターンは、関数に複数の `return` ステートメントが含まれる場合に便利です。  また、このパターンは、例外セーフなコードを記述するのにも役立ちます。  `throw` ステートメントによってスタックがアンワインドされると、RAII オブジェクトのデストラクターが呼び出されます。そのため、リソースが常に正しく削除または解放されます。  
  
 ランタイムには、[concurrency::critical\_section::scoped\_lock](../Topic/critical_section::scoped_lock%20Class.md) クラスや [concurrency::reader\_writer\_lock::scoped\_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md) クラスなど、RAII パターンを使用するいくつかのクラスが定義されています。  これらのヘルパー クラスは*スコープ ロック*と呼ばれます。  これらのクラスは、[concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) オブジェクトや [concurrency::reader\_writer\_lock](../Topic/reader_writer_lock%20Class.md) オブジェクトを操作する場合に役立ちます。  これらのクラスのコンストラクターは、提供された `critical_section` オブジェクトまたは `reader_writer_lock` オブジェクトへのアクセスを取得し、デストラクターはそのオブジェクトへのアクセスを解放します。  相互排他オブジェクトが破棄されると、スコープ ロックはそのオブジェクトへのアクセスを自動的に解放するため、基になるオブジェクトのロックを手動で解除する必要はありません。  
  
 次のクラス `account` について考えます。このクラスは、外部ライブラリで定義されているため、変更できません。  
  
 [!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_4.h)]  
  
 次の例では、`account` オブジェクトに対して複数のトランザクションを並列に実行します。  この例では、`critical_section` オブジェクトを使用して、`account` オブジェクトへのアクセスを同期します。`account` クラスは同時実行セーフではないためです。  各並列操作では、`critical_section::scoped_lock` オブジェクトを使用して、操作が成功または失敗したときに `critical_section` オブジェクトのロックが確実に解除されるようにします。  口座残高が負の場合、`withdraw` 操作は例外をスローして失敗します。  
  
 [!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_5.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
  **Balance before deposit: 1924**  
**Balance after deposit: 2924**  
**Balance before withdrawal: 2924**  
**Balance after withdrawal: \-76**  
**Balance before withdrawal: \-76**  
**Error details:**  
 **negative balance: \-76** RAII パターンを使用して同時実行オブジェクトの有効期間を管理する方法の別の例については、「[チュートリアル: ユーザー インターフェイス スレッドからの処理の除去](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)」、「[方法: Context クラスを使用して協調セマフォを実装する](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)」、および「[方法: オーバーサブスクリプションを使用して待機時間を短縮する](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)」を参照してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="global-scope"></a> グローバル スコープでは同時実行オブジェクトを作成しない  
 グローバル スコープで同時実行オブジェクトを作成すると、アプリケーションでデッドロックやメモリ アクセス違反などの問題が発生する可能性があります。  
  
 たとえば、同時実行ランタイム オブジェクトの作成時にスケジューラがまだ作成されていない場合、既定のスケジューラが作成されます。  グローバル オブジェクトの構築時に作成されるランタイム オブジェクトにより、ランタイムがこの既定のスケジューラを作成します。  ただし、このプロセスでは内部ロックが使用され、同時実行ランタイムのインフラストラクチャをサポートする他のオブジェクトの初期化を妨げる可能性があります。  まだ初期化されていない別のインフラストラクチャ オブジェクトでこの内部ロックが必要になる場合があるため、アプリケーションでデッドロックが発生する可能性があります。  
  
 次の例では、グローバルの [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) オブジェクトを作成する方法を示します。  このパターンは、`Scheduler` クラスだけでなく、同時実行ランタイムに用意されている他のすべての型にも適用されます。  このパターンはアプリケーションの予期しない動作を引き起こす可能性があるため、使用しないことをお勧めします。  
  
 [!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_6.cpp)]  
  
 `Scheduler` オブジェクトの正しい作成例については、「[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)」を参照してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="shared-data"></a> 共有データ セグメントでは同時実行オブジェクトを使用しない  
 同時実行ランタイムでは、[data\_seg](../../preprocessor/data-seg.md) `#pragma` ディレクティブによって作成されるデータ セクションなど、共有データ セクションでの同時実行オブジェクトの使用はサポートされていません。  同時実行オブジェクトがプロセス境界をまたいで共有される場合、ランタイムが不整合な状態または無効な状態になる可能性があります。  
  
 \[[トップ](#top)\]  
  
## 参照  
 [同時実行ランタイムに関するベスト プラクティス](../Topic/Concurrency%20Runtime%20Best%20Practices.md)   
 [並列パターン ライブラリ \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [同期データ構造](../Topic/Synchronization%20Data%20Structures.md)   
 [同期データ構造と Windows API の比較](../Topic/Comparing%20Synchronization%20Data%20Structures%20to%20the%20Windows%20API.md)   
 [方法: Alloc および Free を使用してメモリ パフォーマンスを改善する](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)   
 [方法: オーバーサブスクリプションを使用して待機時間を短縮する](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)   
 [方法: Context クラスを使用して協調セマフォを実装する](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [チュートリアル: ユーザー インターフェイス スレッドからの処理の除去](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)   
 [並列パターン ライブラリに関するベスト プラクティス](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [非同期エージェント ライブラリに関するベスト プラクティス](../Topic/Best%20Practices%20in%20the%20Asynchronous%20Agents%20Library.md)