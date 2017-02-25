---
title: "IThreadProxy 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadProxy 構造体"
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# IThreadProxy 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

実行スレッドの抽象化です。  作成するスケジューラの `SchedulerType` ポリシー キーに応じて、リソース マネージャーは、通常の Win32 スレッドまたはユーザー モード スケジュール可能 \(UMS: User\-Mode Schedulable\) スレッドによってサポートされるスレッド プロキシを許可します。  UMS スレッドは、Windows 7 以上のバージョンの 64 ビット オペレーティング システムでサポートされます。  
  
## 構文  
  
```  
struct IThreadProxy;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IThreadProxy::GetId メソッド](../Topic/IThreadProxy::GetId%20Method.md)|スレッド プロキシの一意の識別子を返します。|  
|[IThreadProxy::SwitchOut メソッド](../Topic/IThreadProxy::SwitchOut%20Method.md)|基になる仮想プロセッサ ルートからコンテキストの関連付けを解除します。|  
|[IThreadProxy::SwitchTo メソッド](../Topic/IThreadProxy::SwitchTo%20Method.md)|現在実行中のコンテキストから別のコンテキストへの協調的なコンテキスト切り替えを実行します。|  
|[IThreadProxy::YieldToSystem メソッド](../Topic/IThreadProxy::YieldToSystem%20Method.md)|呼び出し元のスレッドから、現在のプロセッサ上で実行する準備が整っている別のスレッドに実行を切り替えます。  実行される次のスレッドは、オペレーティング システムによって選択されます。|  
  
## 解説  
 スレッド プロキシは、処理をディスパッチする手段として `IExecutionContext` インターフェイスで表される実行コンテキストに関連付けられます。  
  
## 継承階層  
 `IThreadProxy`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IExecutionContext 構造体](../Topic/IExecutionContext%20Structure.md)   
 [IScheduler 構造体](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IVirtualProcessorRoot 構造体](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)