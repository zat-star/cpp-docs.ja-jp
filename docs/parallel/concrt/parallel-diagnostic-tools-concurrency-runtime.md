---
title: "並列診断ツール (同時実行ランタイム) | Microsoft Docs"
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
  - "並列診断ツール [同時実行ランタイム]"
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 並列診断ツール (同時実行ランタイム)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] には、マルチスレッド アプリケーションのデバッグとプロファイリングを行うための広範なサポートが用意されています。  
  
## デバッグ  
 Visual Studio デバッガーは **\[並列スタック\]** ウィンドウ、**\[並列タスク\]** ウィンドウと **\[並列ウォッチ\]** ウィンドウが含まれています。  詳細については、「[チュートリアル: 並行アプリケーションのデバッグ](../Topic/Walkthrough:%20Debugging%20a%20Parallel%20Application.md)」および「[方法: 並列ウォッチ ウィンドウを使用する](../Topic/How%20to:%20Use%20the%20Parallel%20Watch%20Window.md)」を参照してください。  
  
## プロファイル  
 プロファイリング ツールには、マルチスレッド アプリケーションの他のプログラムとどのようにやり取りをグラフィカル、テーブルの情報を表示する 3 種類のデータ ビューを提供します。  これらのビューにより、対象となる領域をすばやく特定し、グラフィカル表示上のポイントから呼び出し履歴、呼び出しサイトおよびソース コードに移動できます。  詳細については、「[同時実行ビジュアライザー](../Topic/Concurrency%20Visualizer.md)」を参照してください。  
  
## イベント トレーシング  
 同時実行ランタイムでは、[Event Tracing for Windows](http://msdn.microsoft.com/library/windows/desktop/bb968803) \(ETW\) を使用して、各種イベントが発生したときにプロファイラーなどのインストルメンテーション ツールに通知します。  これらのイベントには、スケジューラのアクティブ化または非アクティブ化、コンテキストの開始、終了、ブロック、ブロック解除、または譲渡、並列アルゴリズムの開始または終了も含まれます。  
  
 [同時実行ビジュアライザー](../Topic/Concurrency%20Visualizer.md) などのツールではこの機能が利用されるため、通常、これらのイベントを直接使用する必要はありません。  ただし、これらのイベントはカスタム プロファイラーを開発する場合、またはイベント トレース ツールを使用すると便利です [Xperf](http://go.microsoft.com/fwlink/?LinkID=160628)。  
  
 同時実行ランタイムがこれらのイベントを発生させるのは、トレーシングが有効になっている場合のみです。  イベント トレースと [concurrency::DisableTracing](../Topic/DisableTracing%20Function.md) 関数がトレースを無効にするために [concurrency::EnableTracing](../Topic/EnableTracing%20Function.md) 関数を呼び出します。  
  
 次の表では、イベント トレーシングが有効になっている場合にランタイムが発生させるイベントについて説明します。  
  
|イベント|説明|値|  
|----------|--------|-------|  
|[concurrency::ConcRT\_ProviderGuid](../Topic/ConcRT_ProviderGuid%20Constant.md)|同時実行ランタイムの ETW プロバイダー識別子です。|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[concurrency::ContextEventGuid](../Topic/ContextEventGuid%20Constant.md)|コンテキストに関連するイベントをマークします。|`5727a00f-50be-4519-8256-f7699871fecb`|  
|[concurrency::PPLParallelForEventGuid](../Topic/PPLParallelForEventGuid%20Constant.md)|[concurrency::parallel\_for](../Topic/parallel_for%20Function.md) アルゴリズムの呼び出しの開始と終了をマークします。|`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[concurrency::PPLParallelForeachEventGuid](../Topic/PPLParallelForeachEventGuid%20Constant.md)|[concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) アルゴリズムの呼び出しの開始と終了をマークします。|`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[concurrency::PPLParallelInvokeEventGuid](../Topic/PPLParallelInvokeEventGuid%20Constant.md)|[concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) アルゴリズムの呼び出しの開始と終了をマークします。|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[concurrency::SchedulerEventGuid](../Topic/SchedulerEventGuid%20Constant.md)|[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)に関連するイベントをマークします。|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[concurrency::VirtualProcessorEventGuid](../Topic/VirtualProcessorEventGuid%20Constant.md)|仮想プロセッサに関連するイベントをマークします。|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 次のイベントについては、同時実行ランタイムで定義されていますが、現在は発生しません。  これらのイベントは、将来使用するために予約されています。  
  
-   [concurrency::ConcRTEventGuid](../Topic/ConcRTEventGuid%20Constant.md)  
  
-   [concurrency::ScheduleGroupEventGuid](../Topic/SchedulerEventGuid%20Constant.md)  
  
-   [concurrency::ChoreEventGuid](../Topic/ChoreEventGuid%20Constant.md)  
  
-   [concurrency::LockEventGuid](../Topic/LockEventGuid%20Constant.md)  
  
-   [concurrency::ResourceManagerEventGuid](../Topic/ResourceManagerEventGuid%20Constant.md)  
  
 [concurrency::ConcRT\_EventType](../Topic/ConcRT_EventType%20Enumeration.md) の列挙体は可能なイベントを追跡する操作を指定します。  たとえば、`parallel_for` アルゴリズムの開始時には、`PPLParallelForEventGuid` イベントが発生し、操作として `CONCRT_EVENT_START` が指定されます。  `parallel_for` アルゴリズムから制御が戻される前に、`PPLParallelForEventGuid` イベントが再び発生し、操作として `CONCRT_EVENT_END` が指定されます。  
  
 次の例では、`parallel_for` の呼び出しに対してトレーシングを有効にする方法を示します。  `parallel_for` の最初の呼び出しはトレースされません。その時点では、トレーシングが有効になっていないためです。  `EnableTracing` を呼び出すと、`parallel_for` の 2 回目の呼び出しがトレースされるようになります。  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/CPP/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 ランタイムでは、`EnableTracing` および `DisableTracing` の呼び出し回数も追跡されます。  したがって、`EnableTracing` を複数回呼び出す場合にトレーシングを無効にするには、`DisableTracing` も同じ回数呼び出す必要があります。  
  
## 参照  
 [同時実行ランタイム](../../parallel/concrt/concurrency-runtime.md)