---
title: "IScheduler 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IScheduler 構造体"
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# IScheduler 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

作業スケジューラの抽象化のインターフェイスです。  同時実行ランタイムのリソース マネージャーは、このインターフェイスを使用して作業スケジューラと通信します。  
  
## 構文  
  
```  
struct IScheduler;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IScheduler::AddVirtualProcessors メソッド](../Topic/IScheduler::AddVirtualProcessors%20Method.md)|使用できる一連の仮想プロセッサ ルートをスケジューラに提供します。  個々の `IVirtualProcessorRoot` インターフェイスは、スケジューラに代わって処理を実行できる単一のスレッドを実行する権利を表します。|  
|[IScheduler::GetId メソッド](../Topic/IScheduler::GetId%20Method.md)|スケジューラの一意の識別子を返します。|  
|[IScheduler::GetPolicy メソッド](../Topic/IScheduler::GetPolicy%20Method.md)|スケジューラのポリシーのコピーを返します。  スケジューラのポリシーの詳細については、「[SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md)」を参照してください。|  
|[IScheduler::NotifyResourcesExternallyBusy メソッド](../Topic/IScheduler::NotifyResourcesExternallyBusy%20Method.md)|配列 `ppVirtualProcessorRoots` 内の一連の仮想プロセッサ ルートによって表されるハードウェア スレッドが、現在他のスケジューラによって使用されていることをこのスケジューラに通知します。|  
|[IScheduler::NotifyResourcesExternallyIdle メソッド](../Topic/IScheduler::NotifyResourcesExternallyIdle%20Method.md)|配列 `ppVirtualProcessorRoots` 内の一連の仮想プロセッサ ルートによって表されるハードウェア スレッドが、他のスケジューラによって使用されていないことをこのスケジューラに通知します。|  
|[IScheduler::RemoveVirtualProcessors メソッド](../Topic/IScheduler::RemoveVirtualProcessors%20Method.md)|以前にこのスケジューラに割り当てられた仮想プロセッサ ルートの削除を開始します。|  
|[IScheduler::Statistics メソッド](../Topic/IScheduler::Statistics%20Method.md)|タスクの到着と完了率、およびスケジューラのキューの長さの変更に関係する情報を提供します。|  
  
## 解説  
 リソース マネージャーと通信するカスタム スケジューラを実装する場合は、`IScheduler` インターフェイスの実装を提供する必要があります。  このインターフェイスは、スケジューラとリソース マネージャーを結ぶ双方向通信チャネルの一方の端を表します。  もう一方は、`IResourceManager` インターフェイスと `ISchedulerProxy` インターフェイスで表されます。この 2 つは、リソース マネージャーによって実装されます。  
  
## 継承階層  
 `IScheduler`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey 列挙型](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy クラス](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [IExecutionContext 構造体](../Topic/IExecutionContext%20Structure.md)   
 [IThreadProxy 構造体](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 構造体](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [IResourceManager 構造体](../../../parallel/concrt/reference/iresourcemanager-structure.md)