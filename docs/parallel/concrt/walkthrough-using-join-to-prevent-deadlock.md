---
title: "チュートリアル: join を使用したデッドロックの防止 | Microsoft Docs"
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
  - "防止 (結合を使用してデッドロックを) [同時実行ランタイム]"
  - "デッドロック、防止 [同時実行ランタイム]"
  - "最短一致の結合、例"
  - "join クラス、例"
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# チュートリアル: join を使用したデッドロックの防止
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、[concurrency::join](../Topic/join%20Class.md) クラスを使用してアプリケーションでデッドロックを防止する方法について、"食事する哲学者の問題" を使用して説明します。  ソフトウェア アプリケーションで、2 つ以上のプロセスがそれぞれリソースを確保し、別のプロセスがリソースを解放するのをお互いに待機すると、*デッドロック*が発生します。  
  
 "食事する哲学者の問題" は、リソース セットが複数の同時実行プロセス間で共有される場合に発生する可能性のある一般的な問題の特定の例です。  
  
## 必須コンポーネント  
 このチュートリアルを開始する前に、次のトピックを参照してください。  
  
-   [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)  
  
-   [チュートリアル: エージェント ベースのアプリケーションの作成](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
  
-   [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)  
  
-   [同期データ構造](../Topic/Synchronization%20Data%20Structures.md)  
  
##  <a name="top"></a> セクション  
 このチュートリアルは、次のセクションで構成されています。  
  
-   [食事する哲学者の問題](#problem)  
  
-   [この問題を考慮していない実装](#deadlock)  
  
-   [join を使用したデッドロックの防止](#solution)  
  
##  <a name="problem"></a> 食事する哲学者の問題  
 "食事する哲学者の問題" は、アプリケーションでどのようにデッドロックが発生するかを示します。  この問題では、5 人の哲学者が丸いテーブルを囲んで座っています。  どの哲学者も思索と食事を交互に行っています。  どの哲学者も左隣の哲学者と 1 本の箸を共有する必要があり、また右隣の哲学者とも別の 1 本の箸を共有する必要があります。  次の図は、この配置を表しています。  
  
 ![食事する哲学者の問題](../../parallel/concrt/media/dining_philosophersproblem.png "Dining\_PhilosophersProblem")  
  
 食事をするには、哲学者は 2 本の箸を持つ必要があります。  すべての哲学者が 1 本の箸を持ち、もう 1 本の箸を待つと、どの哲学者も食事することができず、すべての哲学者が餓死することになります。  
  
 \[[トップ](#top)\]  
  
##  <a name="deadlock"></a> この問題を考慮していない実装  
 次の例は、"食事する哲学者の問題" を考慮していない実装を示しています。  [concurrency::agent](../../parallel/concrt/reference/agent-class.md) から派生させた `philosopher` クラスにより、各哲学者は独立して行動できます。  この例では、[concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) オブジェクトの共有配列を使用して、各 `philosopher` オブジェクトに対し、2 本の箸への排他アクセス権を与えています。  
  
 この実装を図に関連付けて説明すると、`philosopher` クラスは 1 人の哲学者を表します。  `int` 変数は、それぞれの箸を表します。  `critical_section` オブジェクトは、箸が置かれる箸置きとして機能します。  `run` メソッドは、哲学者の生命をシミュレートしています。  `think` メソッドは、考える行為をシミュレートしており、`eat` メソッドは、食事する行為をシミュレートしています。  
  
 `philosopher` オブジェクトは、`eat` メソッドを呼び出す前に、両方の `critical_section` オブジェクトをロックして、箸置きから箸が取られたことをシミュレートします。  `eat` の呼び出しの後、`philosopher` オブジェクトは、`critical_section` オブジェクトをロック解除状態に再設定することで、箸を箸置きに戻します。  
  
 `pickup_chopsticks` メソッドは、どこでデッドロックが発生する可能性があるかを示します。  すべての `philosopher` オブジェクトがいずれかのロックにアクセスした場合、どの `philosopher` オブジェクトも続行できません。これは、そのアクセスしたロックが別の `philosopher` オブジェクトにより制御されているためです。  
  
## 例  
  
### 説明  
  
### コード  
 [!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_1.cpp)]  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`philosophers-deadlock.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc philosophers\-deadlock.cpp**  
  
 \[[トップ](#top)\]  
  
##  <a name="solution"></a> join を使用したデッドロックの防止  
 このセクションでは、メッセージ バッファーおよびメッセージ パッシング関数を使用して、デッドロックを発生させないようにする方法について説明します。  
  
 この例を前の例に関連付けて説明すると、`philosopher` クラスでは、各 `critical_section` オブジェクトの代わりに、[concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) オブジェクトおよび `join` オブジェクトが使用されます。  `join` オブジェクトは、哲学者に箸を与える決定者として機能します。  
  
 この例では、`unbounded_buffer` クラスを使用しています。これは、ターゲットが `unbounded_buffer` オブジェクトからメッセージを受け取ったときに、そのメッセージはメッセージ キューから削除されるためです。  これにより、メッセージを保持する `unbounded_buffer` オブジェクトは、箸が使用できることを示すことができます。  メッセージを保持しない `unbounded_buffer` オブジェクトは、箸が使用されていることを示します。  
  
 この例では、最短一致の `join` オブジェクトを使用しています。最短一致の join は、両方の `unbounded_buffer` オブジェクトにメッセージが含まれる場合に限り、各 `philosopher` オブジェクトに対し、両方の箸へのアクセス権を与えるためです。  最長一致の join は、メッセージが使用できるようになるとすぐにメッセージを受け取るため、最長一致の join ではデッドロックは防止されません。  すべての最長一致 `join` オブジェクトがメッセージのいずれかを受け取り、一方で他のメッセージが使用できるようになるのを長時間待つ場合、デッドロックが発生する可能性があります。  
  
 最長一致の join および最短一致の join の詳細、およびさまざまなメッセージ バッファーの違いの詳細については、「[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
#### この例でデッドロックを防止するには  
  
1.  次のコードを例から削除します。  
  
     [!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_2.cpp)]  
  
2.  `philosopher` クラスの `_left` データ メンバーおよび `_right` データ メンバーの型を `unbounded_buffer` に変更します。  
  
     [!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_3.cpp)]  
  
3.  `philosopher` コンストラクターを変更して、パラメーターとして `unbounded_buffer` オブジェクトを受け取るようにします。  
  
     [!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_4.cpp)]  
  
4.  `pickup_chopsticks` メソッドを変更して、最短一致の `join` オブジェクトを使用して両方の箸のメッセージ バッファーからメッセージを受け取るようにします。  
  
     [!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_5.cpp)]  
  
5.  `putdown_chopsticks` メソッドを変更して、両方の箸のメッセージ バッファーにメッセージを送信することで、箸へのアクセス権を放棄するようにします。  
  
     [!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_6.cpp)]  
  
6.  `run` メソッドを変更して、`pickup_chopsticks` メソッドの結果を保持し、それらの結果を `putdown_chopsticks` メソッドに渡すようにします。  
  
     [!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_7.cpp)]  
  
7.  `wmain` 関数の `chopsticks` 変数の宣言を変更して、それぞれが 1 つのメッセージを保持する `unbounded_buffer` オブジェクトの配列にします。  
  
     [!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_8.cpp)]  
  
## 例  
  
### 説明  
 最短一致の `join` オブジェクトを使用してデッドロックの危険性を排除する完全な例を次に示します。  
  
### コード  
 [!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_9.cpp)]  
  
### コメント  
 この例を実行すると、次の出力が生成されます。  
  
  **aristotle ate 50 times.**  
**descartes ate 50 times.**  
**hobbes ate 50 times.**  
**socrates ate 50 times.**  
**plato ate 50 times.**   
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`philosophers-join.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc philosophers\-join.cpp**  
  
 \[[トップ](#top)\]  
  
## 参照  
 [同時実行ランタイムのチュートリアル](../Topic/Concurrency%20Runtime%20Walkthroughs.md)   
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)   
 [同期データ構造](../Topic/Synchronization%20Data%20Structures.md)