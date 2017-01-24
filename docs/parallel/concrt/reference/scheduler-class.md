---
title: "Scheduler クラス | Microsoft Docs"
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
  - "concrt/concurrency::Scheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Scheduler クラス"
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 19
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Scheduler クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

同時実行ランタイム スケジューラの抽象化を表します。  
  
## 構文  
  
```  
class Scheduler;  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Scheduler::Scheduler コンストラクター](../Topic/Scheduler::Scheduler%20Constructor.md)|`Scheduler` クラスのオブジェクトが作成されるのは、ファクトリ メソッドを使用した場合か、暗黙的に作成された場合のみです。|  
|[Scheduler::~Scheduler デストラクター](../Topic/Scheduler::~Scheduler%20Destructor.md)|`Scheduler` クラスのオブジェクトは、そのオブジェクトに対する外部参照が消滅したときに、暗黙的に破棄されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[Scheduler::Attach メソッド](../Topic/Scheduler::Attach%20Method.md)|スケジューラを呼び出し元コンテキストにアタッチします。  このメソッドから制御が戻った後、このスケジューラによって呼び出し元コンテキストが管理され、このスケジューラが現在のスケジューラになります。|  
|[Scheduler::Create メソッド](../Topic/Scheduler::Create%20Method.md)|`_Policy` パラメーターによって動作が指定されたスケジュールを新規に作成し、そのスケジューラに初期参照を設定した後、そのスケジューラへのポインターを返します。|  
|[Scheduler::CreateScheduleGroup メソッド](../Topic/Scheduler::CreateScheduleGroup%20Method.md)|オーバーロードされます。  スケジューラ内で新しいスケジュール グループを作成します。  `_Placement` パラメーターを受け取るバージョンと、そのパラメーターで指定された場所に実行に向かって偏られた新しく作成されたスケジュール グループ内のタスクが実行されます。|  
|[Scheduler::GetNumberOfVirtualProcessors メソッド](../Topic/Scheduler::GetNumberOfVirtualProcessors%20Method.md)|スケジューラの仮想プロセッサの現在の数を返します。|  
|[Scheduler::GetPolicy メソッド](../Topic/Scheduler::GetPolicy%20Method.md)|スケジューラの作成に使用されたポリシーのコピーを返します。|  
|[Scheduler::Id メソッド](../Topic/Scheduler::Id%20Method.md)|スケジューラの一意の識別子を返します。|  
|[Scheduler::IsAvailableLocation メソッド](../Topic/Scheduler::IsAvailableLocation%20Method.md)|指定された位置がスケジューラで使用できるかどうかを判定します。|  
|[Scheduler::Reference メソッド](../Topic/Scheduler::Reference%20Method.md)|スケジューラの参照カウントをインクリメントします。|  
|[Scheduler::RegisterShutdownEvent メソッド](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)|スケジューラがシャットダウンし、自分自身を破棄するとき、`_Event` パラメーターに渡された Windows イベント ハンドルをシグナル状態にします。  イベントがシグナル状態になった時点で、スケジューラに割り当てられていたすべての処理が完了します。  複数のシャットダウン イベントをこのメソッドに登録することもできます。|  
|[Scheduler::Release メソッド](../Topic/Scheduler::Release%20Method.md)|スケジューラの参照カウントをデクリメントします。|  
|[Scheduler::ResetDefaultSchedulerPolicy メソッド](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md)|ランタイムの既定に既定のスケジューラ ポリシーをリセットします。  既定のスケジューラが作成されるときに、ランタイムの既定のポリシー設定が使用されます。|  
|[Scheduler::ScheduleTask メソッド](../Topic/Scheduler::ScheduleTask%20Method.md)|オーバーロードされます。  スケジューラ内の軽量タスクをスケジュールします。  軽量タスクは実行時に決定されたスケジュール グループに配置されます。  `_Placement` パラメーターを受け取るバージョンは、指定された位置に実行に向かって偏られているタスクを実行します。|  
|[Scheduler::SetDefaultSchedulerPolicy メソッド](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)|ユーザー定義のポリシーを使用して既定のスケジューラを作成できるようにします。  このメソッドは、既定のスケジューラがプロセス内に存在しない場合のみ呼び出すことができます。  既定のポリシーを設定すると、`SetDefaultSchedulerPolicy` または [ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md) のメソッドへの有効な呼び出しまで有効です。|  
  
## 解説  
 同時実行ランタイム スケジューラは、アプリケーションによってキューに入れられた作業を実行するために、オペレーティング システムの実行コンテキストに、スレッドなど、マップする実行コンテキストが使用されます。  スケジューラの同時実行レベルは、リソース マネージャーによって許可された仮想プロセッサの数と常に等しくなります。  仮想プロセッサとは、処理リソースを抽象化したものであり、基になるシステムのハードウェア スレッドに対応しています。  指定された時点に 1 つの仮想プロセッサで実行できるスケジューラ コンテキストは 1 つのみです。  
  
 同時実行ランタイムによって、プロセスごとに既定のスケジューラが作成され、並列処理が実行されます。  さらに、独自のスケジューラ インスタンスを作成し、このクラスを使用してそれを操作できます。  
  
## 継承階層  
 `Scheduler`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler Class](../../../parallel/concrt/reference/scheduler-class.md)   
 [PolicyElementKey 列挙型](../Topic/PolicyElementKey%20Enumeration.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)