---
title: "message_processor クラス | Microsoft Docs"
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
  - "agents/concurrency::message_processor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message_processor クラス"
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# message_processor クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`message_processor` クラスは、`message` オブジェクトを処理するための抽象基底クラスです。  メッセージの順序は保証されません。  
  
## 構文  
  
```  
template<  
   class _Type  
>  
class message_processor;  
```  
  
#### パラメーター  
 `_Type`  
 この `message_processor` オブジェクトによって処理されるメッセージ内のペイロードのデータ型。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`type`|`_Type` の型のエイリアス。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[message\_processor::async\_send メソッド](../Topic/message_processor::async_send%20Method.md)|派生クラスでオーバーライドされると、ブロックに非同期的にメッセージを渡します。|  
|[message\_processor::sync\_send メソッド](../Topic/message_processor::sync_send%20Method.md)|派生クラスでオーバーライドされると、ブロックに同期的にメッセージを渡します。|  
|[message\_processor::wait メソッド](../Topic/message_processor::wait%20Method.md)|派生クラスでオーバーライドされると、すべての非同期操作が完了するのを待機します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[message\_processor::process\_incoming\_message メソッド](../Topic/message_processor::process_incoming_message%20Method.md)|派生クラスでオーバーライドされると、ブロックへのメッセージの転送処理を実行します。  新しいメッセージが追加され、キューが空であると検出されるたびに呼び出されます。|  
  
## 継承階層  
 `message_processor`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ordered\_message\_processor クラス](../Topic/ordered_message_processor%20Class.md)