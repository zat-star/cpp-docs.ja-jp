---
title: "agent クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::agent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "agent クラス"
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# agent クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

すべての独立エージェントの基底クラスとして使用されるクラスです。  他のエージェントに状態が表示されないようにしたり、メッセージ渡しでやり取りしたりする目的で使用されます。  
  
## 構文  
  
```  
class agent;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[agent::agent コンストラクター](../Topic/agent::agent%20Constructor.md)|オーバーロードされます。  エージェントを構築します。|  
|[agent::~agent デストラクター](../Topic/agent::~agent%20Destructor.md)|エージェントを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[agent::cancel メソッド](../Topic/agent::cancel%20Method.md)|エージェントの状態を `agent_created` または `agent_runnable` から `agent_canceled` に変更します。|  
|[agent::start メソッド](../Topic/agent::start%20Method.md)|エージェントを `agent_created` 状態から `agent_runnable` 状態に移行させ、実行用にスケジュールします。|  
|[agent::status メソッド](../Topic/agent::status%20Method.md)|エージェントからのステータス情報の同期ソース。|  
|[agent::status\_port メソッド](../Topic/agent::status_port%20Method.md)|エージェントからのステータス情報の非同期ソース。|  
|[agent::wait メソッド](../Topic/agent::wait%20Method.md)|エージェントがタスクを完了するのを待ちます。|  
|[agent::wait\_for\_all メソッド](../Topic/agent::wait_for_all%20Method.md)|指定されたすべてのエージェントがタスクを完了するのを待ちます。|  
|[agent::wait\_for\_one メソッド](../Topic/agent::wait_for_one%20Method.md)|指定されたエージェントのいずれかがタスクを完了するのを待ちます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[agent::done メソッド](../Topic/agent::done%20Method.md)|エージェントを `agent_done` 状態 \(エージェントが完了済みであることを示す\) に移行させます。|  
|[agent::run メソッド](../Topic/agent::run%20Method.md)|エージェントの主なタスクを表します。  `run` は、派生クラスでオーバーライドする必要があります。このメソッドは、エージェントが開始された後に実行する処理を指定します。|  
  
## 解説  
 詳細については、「[非同期エージェント](../../../parallel/concrt/asynchronous-agents.md)」を参照してください。  
  
## 継承階層  
 `agent`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)