---
title: "structured_task_group クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::structured_task_group"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "structured_task_group クラス"
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# structured_task_group クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`structured_task_group` クラスは、並列処理の高度に構造化されたコレクションを表します。  `task_handle` オブジェクトを使用して個々の並列タスクを `structured_task_group` のキューに配置し、それらのタスクが完了するまで待機するか、実行が完了する前にタスク グループを取り消すことができます。取り消すと、実行が開始されていないタスクはすべて中止されます。  
  
## 構文  
  
```  
class structured_task_group;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[structured\_task\_group::structured\_task\_group コンストラクター](../Topic/structured_task_group::structured_task_group%20Constructor.md)|オーバーロードされます。  新しい `structured_task_group` オブジェクトを構築します。|  
|[structured\_task\_group::~structured\_task\_group デストラクター](../Topic/structured_task_group::~structured_task_group%20Destructor.md)|`structured_task_group` オブジェクトを破棄します。  例外が原因でスタック アンワインドを実行した結果、このデストラクターを実行する場合を除いて、このデストラクターを実行する前に、オブジェクトに `wait` メソッドまたは `run_and_wait` メソッドを呼び出す必要があります。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[structured\_task\_group::cancel メソッド](../Topic/structured_task_group::cancel%20Method.md)|このタスク グループをルートとする作業のサブツリーの取り消しをベスト エフォートで試みます。  タスク グループでスケジュールされているすべてのタスクは、可能であれば推移的に取り消されます。|  
|[structured\_task\_group::is\_canceling メソッド](../Topic/structured_task_group::is_canceling%20Method.md)|タスク グループが現在取り消し処理中であるかどうかを呼び出し元に通知します。  これは、必ずしも `structured_task_group` オブジェクトで `cancel` メソッドが呼び出されたことを示しているわけではありません \(ただし、その場合、このメソッドは確実に `true` を返します\)。  `structured_task_group` オブジェクトがインラインで実行されているときに、作業ツリーの上位のタスク グループが既に取り消されていることもあります。  このように、取り消し処理がこの `structured_task_group` オブジェクトを経由することをラインタイムが事前に判定できる場合も、`true` が返されます。|  
|[structured\_task\_group::run メソッド](../Topic/structured_task_group::run%20Method.md)|オーバーロードされます。  `structured_task_group` オブジェクトでタスクをスケジュールします。  `_Task_handle` パラメーターに渡される `task_handle` オブジェクトの有効期間は、呼び出し元によって管理されます。  `_Placement` パラメーターを受け取るバージョンと、そのパラメーターで指定された場所に実行に向かって偏られているタスクを実行します。|  
|[structured\_task\_group::run\_and\_wait メソッド](../Topic/structured_task_group::run_and_wait%20Method.md)|オーバーロードされます。  取り消し処理を完全にサポートするために、`structured_task_group` オブジェクトを使用して呼び出し元コンテキストでインラインで実行されるようにタスクをスケジュールします。  `task_handle` オブジェクトが `run_and_wait` にパラメーターとして渡される場合、`task_handle` オブジェクトの有効期間は呼び出し元によって管理されます。  その後、`structured_task_group` オブジェクトのすべての処理が完了するか、取り消されるまで待機します。|  
|[structured\_task\_group::wait メソッド](../Topic/structured_task_group::wait%20Method.md)|`structured_task_group` のすべての処理が完了するか、取り消されるまで待機します。|  
  
## 解説  
 パフォーマンスを向上させるために、`structured_task_group` オブジェクトの使用には、次のような厳しい制限がいくつかあります。  
  
-   単一の `structured_task_group` オブジェクトを複数のスレッドで使用できない。  `structured_task_group` オブジェクトに対するすべての操作は、オブジェクトを作成したスレッドで実行される必要があります。  この規則の例外には、メンバー関数 `cancel` および `is_canceling` の 2 つがあります。  タスクで取り消し操作を使用していない場合、オブジェクトがラムダ式のキャプチャ リストに含まれず、タスク内で使用されることがあります。  
  
-   `structured_task_group` オブジェクトにスケジュールされるすべてのタスクは、有効期間を明示的に管理する必要がある `task_handle` オブジェクトの使用によってスケジュールされる。  
  
-   グループが複数ある場合、それらのグループは絶対的に入れ子にされた順序でのみ使用できる。  `structured_task_group` オブジェクトを 2 つ宣言した場合、1 番目に宣言したオブジェクト \(外側のオブジェクト\) で `cancel` または `is_canceling` 以外の任意のメソッドを呼び出す前に、2 番目に宣言したオブジェクト \(内側のオブジェクト\) を破棄する必要があります。  この条件は、同じスコープ内または機能的に入れ子になったスコープ内で複数の `structured_task_group` オブジェクトを単純に宣言した場合にも、`run` メソッドまたは `run_and_wait` メソッドを使用して `structured_task_group` のキューに配置されたタスクの場合にも当てはまります。  
  
-   一般的な `task_group` クラスとは異なり、`structured_task_group` クラスの状態はすべて最終である。  タスクをグループに完了するまで待機すると、をキューと同じグループを使用することはできません。  
  
 詳細については、「[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。  
  
## 継承階層  
 `structured_task_group`  
  
## 必要条件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group クラス](../Topic/task_group%20Class.md)   
 [task\_handle クラス](../../../parallel/concrt/reference/task-handle-class.md)