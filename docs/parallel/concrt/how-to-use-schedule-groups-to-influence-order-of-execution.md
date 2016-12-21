---
title: "方法: スケジュール グループを使用して実行順序に影響を与える | Microsoft Docs"
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
  - "スケジュール グループ、使用 [同時実行ランタイム]"
  - "使用 (スケジュール グループを) [同時実行ランタイム]"
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: スケジュール グループを使用して実行順序に影響を与える
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

同時実行ランタイムでは、タスクをスケジュールする順序は非確定的です。  ただし、スケジューリング ポリシーを使用して、タスクの実行順序に影響を与えることができます。  ここでは、[concurrency::SchedulingProtocol](../Topic/PolicyElementKey%20Enumeration.md) スケジューラ ポリシーと共にスケジュール グループを使用して、タスクの実行順序に影響を与える方法について説明します。  
  
 例では、一連のタスクを 2 回、それぞれ異なるスケジューリング ポリシーを使用して実行します。  どちらのポリシーでも、処理リソースの最大数は 2 つに制限されます。  最初の実行では `EnhanceScheduleGroupLocality`  ポリシー \(既定\) を使用し、2 回目の実行では `EnhanceForwardProgress` ポリシーを使用します。  `EnhanceScheduleGroupLocality` ポリシーでは、1 つのスケジュール グループ内の各タスクが終了または生成するまですべてのタスクを実行します。  `EnhanceForwardProgress` ポリシーでは、1 つのタスクが終了または生成すると、ラウンドロビン方式で次のスケジュール グループに移動します。  
  
 各スケジュール グループに関連するタスクが含まれている場合、`EnhanceScheduleGroupLocality` ポリシーを使用すると、通常、タスク間でキャッシュの局所性が保持されるため、パフォーマンスが向上します。  `EnhanceForwardProgress` ポリシーを使用すると、タスクを次に進めることができるため、スケジュール グループ間で公平にスケジュールを設定する必要がある場合に便利です。  
  
## 使用例  
 この例では、[concurrency::agent](../../parallel/concrt/reference/agent-class.md) から派生する `work_yield_agent` クラスを定義します。  `work_yield_agent` クラスでは、1 つの作業単位を実行し、現在のコンテキストを生成した後、別の作業単位を実行します。  エージェントは、他のコンテキストが実行できるように、[concurrency::wait](../Topic/wait%20Function.md) 関数を使用して、現在のコンテキストを協調的に譲渡します。  
  
 この例では、`work_yield_agent` オブジェクトを 4 つ作成します。  スケジューラ ポリシーを設定してエージェントの実行順序に影響を与える方法がわかるように、最初の 2 つのエージェントと残りの 2 つのエージェントを別々のスケジュール グループに関連付けます。  また、[concurrency::CurrentScheduler::CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md) メソッドを使用して、[concurrency::ScheduleGroup](../Topic/ScheduleGroup%20Class.md) オブジェクトを作成します。  例では、4 つすべてのエージェントを 2 回実行します。それぞれの実行で、異なるスケジューリング ポリシーを使用します。  
  
 [!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/CPP/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **Using EnhanceScheduleGroupLocality...**  
**group 0,task 0: first loop...**  
**group 0,task 1: first loop...**  
**group 0,task 0: waiting...**  
**group 1,task 0: first loop...**  
**group 0,task 1: waiting...**  
**group 1,task 1: first loop...**  
**group 1,task 0: waiting...**  
**group 0,task 0: second loop...**  
**group 1,task 1: waiting...**  
**group 0,task 1: second loop...**  
**group 0,task 0: finished...**  
**group 1,task 0: second loop...**  
**group 0,task 1: finished...**  
**group 1,task 1: second loop...**  
**group 1,task 0: finished...**  
**group 1,task 1: finished...**  
**Using EnhanceForwardProgress...**  
**group 0,task 0: first loop...**  
**group 1,task 0: first loop...**  
**group 0,task 0: waiting...**  
**group 0,task 1: first loop...**  
**group 1,task 0: waiting...**  
**group 1,task 1: first loop...**  
**group 0,task 1: waiting...**  
**group 0,task 0: second loop...**  
**group 1,task 1: waiting...**  
**group 1,task 0: second loop...**  
**group 0,task 0: finished...**  
**group 0,task 1: second loop...**  
**group 1,task 0: finished...**  
**group 1,task 1: second loop...**  
**group 0,task 1: finished...**  
**group 1,task 1: finished...** どちらのポリシーでも、イベントの順序は同じになります。  ただし、`EnhanceScheduleGroupLocality` を使用するポリシーでは、最初のスケジュール グループに属するエージェントを両方開始した後に、2 番目のグループに属するエージェントを開始します。  `EnhanceForwardProgress` を使用するポリシーでは、最初のスケジュール グループのエージェントを 1 つ開始した後、2 番目のグループの最初のエージェントを開始します。  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`scheduling-protocol.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc scheduling\-protocol.cpp**  
  
## 参照  
 [スケジュール グループ](../../parallel/concrt/schedule-groups.md)   
 [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)