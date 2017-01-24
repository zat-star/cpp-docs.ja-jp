---
title: "IExecutionResource 構造体 | Microsoft Docs"
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
  - "concrtrm/concurrency::IExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IExecutionResource 構造体"
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
caps.latest.revision: 16
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IExecutionResource 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

ハードウェア スレッドの抽象化です。  
  
## 構文  
  
```  
struct IExecutionResource;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IExecutionResource::CurrentSubscriptionLevel メソッド](../Topic/IExecutionResource::CurrentSubscriptionLevel%20Method.md)|アクティブ化された仮想プロセッサ ルートの数と、この実行リソースが表す基になるハードウェア スレッドに現在関連付けられているサブスクライブされた外部スレッドの数を返します。|  
|[IExecutionResource::GetExecutionResourceId メソッド](../Topic/IExecutionResource::GetExecutionResourceId%20Method.md)|この実行リソースが表すハードウェア スレッドの一意の識別子を返します。|  
|[IExecutionResource::GetNodeId メソッド](../Topic/IExecutionResource::GetNodeId%20Method.md)|この実行リソースが属しているプロセッサ ノードの一意の識別子を返します。|  
|[IExecutionResource::Remove メソッド](../Topic/IExecutionResource::Remove%20Method.md)|この実行リソースをリソース マネージャーに返します。|  
  
## 解説  
 実行リソースはスタンドアロンで存在する場合と、仮想プロセッサ ルートに関連付けられる場合とがあります。  スタンドアロンの実行リソースは、アプリケーション内のスレッドがスレッド サブスクリプションを作成したときに作成されます。  [ISchedulerProxy::SubscribeThread](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md) メソッドおよび [ISchedulerProxy::RequestInitialVirtualProcessors](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md) メソッドは、スレッド サブスクリプションを作成し、サブスクリプションを表す `IExecutionResource` インターフェイスを返します。  スレッド サブスクリプションの作成は、スケジューラのキューに格納されている作業に特定のスレッドが \(リソース マネージャーによってスケジューラに割り当てられる仮想プロセッサ ルートと共に\) 参加する、ということをリソース マネージャーに伝える方法の 1 つです。  リソース マネージャーは、その情報を使用することによって、ハードウェア スレッドのオーバーサブスクリプションを可能な限り防ぎます。  
  
## 継承階層  
 `IExecutionResource`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IVirtualProcessorRoot 構造体](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [ISchedulerProxy::SubscribeCurrentThread メソッド](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)   
 [ISchedulerProxy::RequestInitialVirtualProcessors メソッド](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)