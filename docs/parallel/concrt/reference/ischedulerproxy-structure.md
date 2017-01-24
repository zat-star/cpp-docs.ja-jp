---
title: "ISchedulerProxy 構造体 | Microsoft Docs"
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
  - "concrtrm/concurrency::ISchedulerProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISchedulerProxy 構造体"
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ISchedulerProxy 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

スケジューラは、このインターフェイスを使用して同時実行ランタイムのリソース マネージャーと通信して、リソース割り当てをネゴシエートします。  
  
## 構文  
  
```  
struct ISchedulerProxy;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ISchedulerProxy::BindContext メソッド](../Topic/ISchedulerProxy::BindContext%20Method.md)|実行コンテキストをスレッド プロキシに関連付けます \(まだ関連付けられていない場合\)。|  
|[ISchedulerProxy::CreateOversubscriber メソッド](../Topic/ISchedulerProxy::CreateOversubscriber%20Method.md)|既存の実行リソースに関連付けられているハードウェア スレッドに新しい仮想プロセッサ ルートを作成します。|  
|[ISchedulerProxy::RequestInitialVirtualProcessors メソッド](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)|仮想プロセッサ ルートの最初の割り当てを要求します。  仮想プロセッサ ルート 1 つにつき、スケジューラの処理を実行するためのスレッドを 1 つ実行できます。|  
|[ISchedulerProxy::Shutdown メソッド](../Topic/ISchedulerProxy::Shutdown%20Method.md)|スケジューラの終了処理中であることをリソース マネージャーに通知します。  これにより、リソース マネージャーは、スケジューラに割り当てられたすべてのリソースを直ちに解放します。|  
|[ISchedulerProxy::SubscribeCurrentThread メソッド](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)|現在のスレッドをリソース マネージャーに登録して、このスケジューラに関連付けます。|  
|[ISchedulerProxy::UnbindContext メソッド](../Topic/ISchedulerProxy::UnbindContext%20Method.md)|`pContext` パラメーターで指定された実行コンテキストに対するスレッド プロキシの関連付けを解除し、それをスレッド プロキシ ファクトリの空きプールに返します。  このメソッドは、[ISchedulerProxy::BindContext](../Topic/ISchedulerProxy::BindContext%20Method.md) メソッドを通じて関連付けられ、さらに [IThreadProxy::SwitchTo](../Topic/IThreadProxy::SwitchTo%20Method.md) メソッドの呼び出しで `pContext` パラメーターとして渡されることにより開始されていない実行コンテキストでのみ、呼び出すことができます。|  
  
## 解説  
 リソース マネージャーは、[IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md) メソッドを使用して登録されたすべてのスケジューラに、`ISchedulerProxy` インターフェイスを渡します。  
  
## 継承階層  
 `ISchedulerProxy`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IScheduler 構造体](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IThreadProxy 構造体](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 構造体](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [IResourceManager 構造体](../../../parallel/concrt/reference/iresourcemanager-structure.md)