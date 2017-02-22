---
title: "timer クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::timer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "timer クラス"
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# timer クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`timer` メッセージング ブロックは単一のターゲットを持つ `source_block` であり、指定された時間の経過後か、特定の間隔で、メッセージをターゲットに送信することができます。  
  
## 構文  
  
```  
template<  
   class _Type  
>  
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<_Type>>>;  
```  
  
#### パラメーター  
 `_Type`  
 このブロックの出力メッセージのペイロード型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[timer::timer コンストラクター](../Topic/timer::timer%20Constructor.md)|オーバーロードされます。  指定されたメッセージを指定された間隔の後で送信する `timer` メッセージング ブロックを構築します。|  
|[timer::~timer デストラクター](../Topic/timer::~timer%20Destructor.md)|`timer` メッセージング ブロックを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[timer::pause メソッド](../Topic/timer::pause%20Method.md)|`timer` メッセージング ブロックを停止します。  `timer` メッセージング ブロックを繰り返す場合、後で `start()` を呼び出すことで再開できます。  非繰り返しタイマーの場合、この呼び出しは `stop` の呼び出しと効果が同じになります。|  
|[timer::start メソッド](../Topic/timer::start%20Method.md)|`timer` メッセージング ブロックを開始します。  このメソッドの呼び出し後に指定されたミリ秒数が経過すると、指定された値が `message` として下位のレベルに伝達されます。|  
|[timer::stop メソッド](../Topic/timer::stop%20Method.md)|`timer` メッセージング ブロックを停止します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[timer::accept\_message メソッド](../Topic/timer::accept_message%20Method.md)|この `timer` メッセージング ブロックによって提供されたメッセージを受け入れ、所有権を呼び出し元に移譲します。|  
|[timer::consume\_message メソッド](../Topic/timer::consume_message%20Method.md)|この `timer` によって以前に提供され、ターゲットによって予約されたメッセージを使用して、所有権を呼び出し元に移譲します。|  
|[timer::link\_target\_notification メソッド](../Topic/timer::link_target_notification%20Method.md)|新しいターゲットがこの `timer` メッセージング ブロックにリンクされたことを通知するコールバックです。|  
|[timer::propagate\_to\_any\_targets メソッド](../Topic/timer::propagate_to_any_targets%20Method.md)|`timer` ブロックによって生成されたメッセージをリンクされたすべてのターゲットに提供することを試みます。|  
|[timer::release\_message メソッド](../Topic/timer::release_message%20Method.md)|以前に行われたメッセージの予約を解放します。\([source\_block::release\_message](../Topic/source_block::release_message%20Method.md) をオーバーライドします。\)|  
|[timer::reserve\_message メソッド](../Topic/timer::reserve_message%20Method.md)|この `timer` メッセージング ブロックによって以前に提供されたメッセージを予約します。\([source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md) をオーバーライドします。\)|  
|[timer::resume\_propagation メソッド](../Topic/timer::resume_propagation%20Method.md)|予約が解放された後で反映を再開します。\([source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md) をオーバーライドします。\)|  
  
## 解説  
 詳細については、「[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
## 継承階層  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 `timer`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)