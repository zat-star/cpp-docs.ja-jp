---
title: "DispatchState 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::DispatchState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DispatchState 構造体"
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# DispatchState 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`DispatchState` 構造体は、状態を `IExecutionContext::Dispatch` メソッドに転送するために使用されます。  `Dispatch` メソッドが `IExecutionContext` インターフェイスで呼び出される状況を示します。  
  
## 構文  
  
```  
struct DispatchState;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[DispatchState::DispatchState コンストラクター](../Topic/DispatchState::DispatchState%20Constructor.md)|新しい `DispatchState` オブジェクトを構築します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[DispatchState::m\_dispatchStateSize データ メンバー](../Topic/DispatchState::m_dispatchStateSize%20Data%20Member.md)|バージョン管理に使用するこの構造体のサイズ。|  
|[DispatchState::m\_fIsPreviousContextAsynchronouslyBlocked データ メンバー](../Topic/DispatchState::m_fIsPreviousContextAsynchronouslyBlocked%20Data%20Member.md)|前のコンテキストが非同期にブロックされたことにより、このコンテキストが `Dispatch` メソッドに入ったかどうかを示します。  これは UMS スケジュール コンテキストでのみ使用され、他のすべての実行コンテキストの値 `0` に設定されます。|  
|[DispatchState::m\_reserved データ メンバー](../Topic/DispatchState::m_reserved%20Data%20Member.md)|将来、情報を渡すために予約されているビット。|  
  
## 継承階層  
 `DispatchState`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IExecutionContext::Dispatch メソッド](../Topic/IExecutionContext::Dispatch%20Method.md)