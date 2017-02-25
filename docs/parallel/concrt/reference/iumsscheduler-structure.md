---
title: "IUMSScheduler 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSScheduler 構造体"
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# IUMSScheduler 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

同時実行ランタイムのリソース マネージャーによってユーザー モード スケジュール可能 \(UMS\) スレッドが渡される必要がある作業スケジューラの抽象化のインターフェイスです。  リソース マネージャーでは、このインターフェイスを使用して UMS スレッド スケジューラと通信します。  `IUMSScheduler` インターフェイスは `IScheduler` インターフェイスを継承します。  
  
## 構文  
  
```  
struct IUMSScheduler : public IScheduler;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IUMSScheduler::SetCompletionList メソッド](../Topic/IUMSScheduler::SetCompletionList%20Method.md)|UMS スレッド スケジューラに `IUMSCompletionList` インターフェイスを割り当てます。|  
  
## 解説  
 リソース マネージャーと通信するカスタム スケジューラを実装するときに、スケジューラに Win32 スレッドではなく UMS スレッドを渡す場合には、`IUMSScheduler` インターフェイスの実装を提供する必要があります。  さらに、スケジューラ ポリシー キー `SchedulerKind` のポリシー値を `UmsThreadDefault` に設定する必要があります。  ポリシーによって UMS スレッドが指定される場合、[IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md) メソッドにパラメーターとして渡される `IScheduler` インターフェイスは、`IUMSScheduler` インターフェイスであることが必要です。  
  
 リソース マネージャーは、UMS 機能を持つオペレーティング システムでのみ、UMS スレッドを渡します。UMS スレッドは、Windows 7 以上の 64 ビット版オペレーティング システムでサポートされます。  `SchedulerKind` キーの値が `UmsThreadDefault` に設定されているスケジューラ ポリシーを作成するとき、基になるプラットフォームで UMS がサポートされていない場合、そのポリシーの `SchedulerKind` キーの値は `ThreadScheduler` に変更されます。  UMS スレッドを受け取ることを想定する場合は、このポリシーの値を必ず確認してください。  
  
 `IUMSScheduler` インターフェイスは、スケジューラとリソース マネージャーを結ぶ双方向チャネルの一方の端を表します。  もう一方は、`IResourceManager` インターフェイスと `ISchedulerProxy` インターフェイスで表されます。この 2 つは、リソース マネージャーによって実装されます。  
  
## 継承階層  
 [IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey 列挙型](../Topic/PolicyElementKey%20Enumeration.md)   
 [IScheduler 構造体](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IUMSCompletionList 構造体](../../../parallel/concrt/reference/iumscompletionlist-structure.md)   
 [IResourceManager 構造体](../../../parallel/concrt/reference/iresourcemanager-structure.md)