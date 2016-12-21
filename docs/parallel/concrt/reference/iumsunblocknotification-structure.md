---
title: "IUMSUnblockNotification 構造体 | Microsoft Docs"
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
  - "concrtrm/concurrency::IUMSUnblockNotification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSUnblockNotification 構造体"
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUMSUnblockNotification 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

ブロックされ、スケジューラの指定されたスケジュール コンテキストに制御を戻すことをトリガーされたスレッド プロキシが、ブロック解除され、スケジュールできる状態であることを示す、リソース マネージャーからの通知を表します。  このインターフェイスは、`GetContext` メソッドから返される、スレッド プロキシの関連付けられた実行コンテキストが再スケジュールされると無効になります。  
  
## 構文  
  
```  
struct IUMSUnblockNotification;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IUMSUnblockNotification::GetContext メソッド](../Topic/IUMSUnblockNotification::GetContext%20Method.md)|ブロック解除を行ったスレッド プロキシに関連付けられている実行コンテキストの `IExecutionContext` インターフェイスを返します。  このメソッドから制御が返され、基になる実行コンテキストが `IThreadProxy::SwitchTo` メソッドの呼び出しを経由して再スケジュールされると、このインターフェイスは有効ではなくなります。|  
|[IUMSUnblockNotification::GetNextUnblockNotification メソッド](../Topic/IUMSUnblockNotification::GetNextUnblockNotification%20Method.md)|`IUMSCompletionList::GetUnblockNotifications` メソッドから返されるチェーン内の次の `IUMSUnblockNotification` インターフェイスを返します。|  
  
## 継承階層  
 `IUMSUnblockNotification`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler 構造体](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [IUMSCompletionList 構造体](../../../parallel/concrt/reference/iumscompletionlist-structure.md)