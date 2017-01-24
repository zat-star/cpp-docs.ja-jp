---
title: "transformer クラス | Microsoft Docs"
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
  - "agents/concurrency::transformer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "transformer クラス"
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
caps.latest.revision: 22
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# transformer クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`transformer` メッセージング ブロックは、単一のターゲットと複数のソースを持つ順序付けられた `propagator_block` であり、1 つの種類のメッセージを複数受け入れ、別の種類のメッセージを無制限に格納することができます。  
  
## 構文  
  
```  
template<  
   class _Input,  
   class _Output  
>  
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>, multi_link_registry<ISource<_Input>>>;  
```  
  
#### パラメーター  
 `_Input`  
 このバッファーが受け入れるメッセージのペイロード型。  
  
 `_Output`  
 このバッファーが格納し、外部に転送するメッセージのペイロード型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[transformer::transformer コンストラクター](../Topic/transformer::transformer%20Constructor.md)|オーバーロードされます。  `transformer` メッセージング ブロックを構築します。|  
|[transformer::~transformer デストラクター](../Topic/transformer::~transformer%20Destructor.md)|`transformer` メッセージング ブロックを破棄します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[transformer::accept\_message メソッド](../Topic/transformer::accept_message%20Method.md)|この `transformer` メッセージング ブロックによって提供されたメッセージを受け入れ、所有権を呼び出し元に移譲します。|  
|[transformer::consume\_message メソッド](../Topic/transformer::consume_message%20Method.md)|この `transformer` によって以前に提供され、ターゲットによって予約されたメッセージを使用して、所有権を呼び出し元に移譲します。|  
|[transformer::link\_target\_notification メソッド](../Topic/transformer::link_target_notification%20Method.md)|新しいターゲットがこの `transformer` メッセージング ブロックにリンクされたことを通知するコールバックです。|  
|[transformer::propagate\_message メソッド](../Topic/transformer::propagate_message%20Method.md)|`ISource` ブロックからこの `transformer` メッセージング ブロックにメッセージを非同期に渡します。  このメソッドは、ソース ブロックから呼び出されたときに `propagate` メソッドによって呼び出されます。|  
|[transformer::propagate\_to\_any\_targets メソッド](../Topic/transformer::propagate_to_any_targets%20Method.md)|入力メッセージに対してトランスフォーマー関数を実行します。|  
|[transformer::release\_message メソッド](../Topic/transformer::release_message%20Method.md)|以前に行われたメッセージの予約を解放します。\([source\_block::release\_message](../Topic/source_block::release_message%20Method.md) をオーバーライドします。\)|  
|[transformer::reserve\_message メソッド](../Topic/transformer::reserve_message%20Method.md)|この `transformer` メッセージング ブロックによって以前に提供されたメッセージを予約します。\([source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md) をオーバーライドします。\)|  
|[transformer::resume\_propagation メソッド](../Topic/transformer::resume_propagation%20Method.md)|予約が解放された後で反映を再開します。\([source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md) をオーバーライドします。\)|  
|[transformer::send\_message メソッド](../Topic/transformer::send_message%20Method.md)|`ISource` ブロックからこの `transformer` メッセージング ブロックにメッセージを同期的に渡します。  このメソッドは、ソース ブロックから呼び出されたときに `send` メソッドによって呼び出されます。|  
|[transformer::supports\_anonymous\_source メソッド](../Topic/transformer::supports_anonymous_source%20Method.md)|`supports_anonymous_source` のメソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け取ることができることを示すためにオーバーライドします。オーバーライド \([ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\)。|  
  
## 解説  
 詳細については、「[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
## 継承階層  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `transformer`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [call クラス](../../../parallel/concrt/reference/call-class.md)