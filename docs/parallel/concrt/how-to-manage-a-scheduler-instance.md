---
title: "方法: スケジューラ インスタンスを管理する | Microsoft Docs"
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
  - "管理 (スケジューラ インスタンスを) [同時実行ランタイム]"
  - "スケジューラ インスタンス、管理 [同時実行ランタイム]"
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 方法: スケジューラ インスタンスを管理する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スケジューラ インスタンスにより、特定のスケジューリング ポリシーと各種の作業負荷を関連付けることができます。  このトピックには、スケジューラ インスタンスを作成および管理する方法を示す 2 つの基本的な例が含まれています。  
  
 例では、既定のスケジューラ ポリシーを使用するスケジューラを作成します。  カスタム ポリシーを使用するスケジューラを作成する例については、「[方法: 特定のスケジューラ ポリシーを指定する](../Topic/How%20to:%20Specify%20Specific%20Scheduler%20Policies.md)」を参照してください。  
  
### アプリケーションのスケジューラ インスタンスを管理するには  
  
1.  スケジューラが使用するポリシー値が含まれる [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) オブジェクトを作成します。  
  
2.  [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md) メソッドまたは [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) メソッドを呼び出して、スケジューラ インスタンスを作成します。  
  
     `Scheduler::Create` メソッドを使用する場合は、スケジューラを現在のコンテキストに関連付ける必要があるときに [concurrency::Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md) メソッドを呼び出します。  
  
3.  [CreateEvent](http://msdn.microsoft.com/library/windows/desktop/ms682396) 関数を呼び出して、非シグナルの自動リセット イベント オブジェクトへのハンドルを作成します。  
  
4.  作成したイベント オブジェクトへのハンドルを [concurrency::CurrentScheduler::RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md) メソッドまたは [concurrency::Scheduler::RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md) メソッドに渡します。  これにより、スケジューラが破棄されるときに設定されるイベントが登録されます。  
  
5.  現在のスケジューラでスケジュールするタスクを実行します。  
  
6.  [concurrency::CurrentScheduler::Detach](../Topic/CurrentScheduler::Detach%20Method.md) メソッドを呼び出して現在のスケジューラをデタッチし、次に以前のスケジューラを現在のスケジューラとして復元します。  
  
     `Scheduler::Create` メソッドを使用する場合は、[concurrency::Scheduler::Release](../Topic/Scheduler::Release%20Method.md) メソッドを呼び出して、`Scheduler` オブジェクトの参照カウントをデクリメントします。  
  
7.  スケジューラがシャットダウンするのを待機するために、イベントへのハンドルを [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032) 関数に渡します。  
  
8.  [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) 関数を呼び出して、イベント オブジェクトへのハンドルを閉じます。  
  
## 使用例  
 次のコードに、スケジューラ インスタンスを管理するための 2 つの方法を示します。  どちらの例でも、最初に既定のスケジューラを使用して、現在のスケジューラの一意の識別子を印刷するタスクを実行します。  次に、スケジューラ インスタンスを使用して同じタスクを再び実行します。  最後に、既定のスケジューラを現在のスケジューラとして復元した後、もう一度同じタスクを実行します。  
  
 1 つ目の例では、[concurrency::CurrentScheduler](../Topic/CurrentScheduler%20Class.md) クラスを使用して、スケジューラ インスタンスを作成し、それを現在のコンテキストに関連付けています。  2 つ目の例では、[concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) クラスを使用して同じタスクを実行しています。  通常は、現在のスケジューラを操作するのに `CurrentScheduler` クラスを使用します。  `Scheduler` クラスを使用する 2 つ目の例は、スケジューラを現在のコンテキストに関連付けるタイミングを制御したり、特定のスケジューラを特定のタスクに関連付けたりする場合に有用です。  
  
 [!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/CPP/how-to-manage-a-scheduler-instance_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **Using CurrentScheduler class...**  
**Current scheduler id: 0**  
**Creating and attaching scheduler...**  
**Current scheduler id: 1**  
**Detaching scheduler...**  
**Current scheduler id: 0**  
**Using Scheduler class...**  
**Current scheduler id: 0**  
**Creating scheduler...**  
**Attaching scheduler...**  
**Current scheduler id: 2**  
**Detaching scheduler...**  
**Current scheduler id: 0**   
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`scheduler-instance.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc scheduler\-instance.cpp**  
  
## 参照  
 [スケジューラ インスタンス](../../parallel/concrt/scheduler-instances.md)   
 [方法: 特定のスケジューラ ポリシーを指定する](../Topic/How%20to:%20Specify%20Specific%20Scheduler%20Policies.md)