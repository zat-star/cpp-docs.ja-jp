---
title: "overwrite_buffer クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::overwrite_buffer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "overwrite_buffer クラス"
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# overwrite_buffer クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`overwrite_buffer` メッセージング ブロックは、一度に 1 つのメッセージを格納することができる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。  新しいメッセージが与えられると、それまで格納されていたメッセージは上書きされます。  
  
## 構文  
  
```  
template<  
   class _Type  
>  
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<_Type>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### パラメーター  
 `_Type`  
 このバッファーが格納し、反映するメッセージのペイロード型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[overwrite\_buffer::overwrite\_buffer コンストラクター](../Topic/overwrite_buffer::overwrite_buffer%20Constructor.md)|オーバーロードされます。  `overwrite_buffer` メッセージング ブロックを構築します。|  
|[overwrite\_buffer::~overwrite\_buffer デストラクター](../Topic/overwrite_buffer::~overwrite_buffer%20Destructor.md)|`overwrite_buffer` メッセージング ブロックを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[overwrite\_buffer::has\_value メソッド](../Topic/overwrite_buffer::has_value%20Method.md)|この `overwrite_buffer` メッセージング ブロックが既に値を持っているかどうかをチェックします。|  
|[overwrite\_buffer::value メソッド](../Topic/overwrite_buffer::value%20Method.md)|`overwrite_buffer` メッセージング ブロックに格納されるメッセージの現在のペイロードへの参照を取得します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[overwrite\_buffer::accept\_message メソッド](../Topic/overwrite_buffer::accept_message%20Method.md)|この `overwrite_buffer` メッセージング ブロックによって提供されたメッセージを受け入れ、そのメッセージのコピーを呼び出し元に返します。|  
|[overwrite\_buffer::consume\_message メソッド](../Topic/overwrite_buffer::consume_message%20Method.md)|この `overwrite_buffer` メッセージング ブロックによって以前に提供され、ターゲットによって予約されたメッセージを使用して、メッセージのコピーを呼び出し元に返します。|  
|[overwrite\_buffer::link\_target\_notification メソッド](../Topic/overwrite_buffer::link_target_notification%20Method.md)|新しいターゲットがこの `overwrite_buffer` メッセージング ブロックにリンクされたことを通知するコールバックです。|  
|[overwrite\_buffer::propagate\_message メソッド](../Topic/overwrite_buffer::propagate_message%20Method.md)|`ISource` ブロックからこの `overwrite_buffer` メッセージング ブロックにメッセージを非同期に渡します。  このメソッドは、ソース ブロックから呼び出されたときに `propagate` メソッドによって呼び出されます。|  
|[overwrite\_buffer::propagate\_to\_any\_targets メソッド](../Topic/overwrite_buffer::propagate_to_any_targets%20Method.md)|`message` `_PMessage` をこの `overwrite_buffer` メッセージング ブロックに配置し、それをリンクされたすべてのターゲットに提供します。|  
|[overwrite\_buffer::release\_message メソッド](../Topic/overwrite_buffer::release_message%20Method.md)|以前に行われたメッセージの予約を解放します。\([source\_block::release\_message](../Topic/source_block::release_message%20Method.md) をオーバーライドします。\)|  
|[overwrite\_buffer::reserve\_message メソッド](../Topic/overwrite_buffer::reserve_message%20Method.md)|この `overwrite_buffer` メッセージング ブロックによって以前に提供されたメッセージを予約します。\([source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md) をオーバーライドします。\)|  
|[overwrite\_buffer::resume\_propagation メソッド](../Topic/overwrite_buffer::resume_propagation%20Method.md)|予約が解放された後で反映を再開します。\([source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md) をオーバーライドします。\)|  
|[overwrite\_buffer::send\_message メソッド](../Topic/overwrite_buffer::send_message%20Method.md)|`ISource` ブロックからこの `overwrite_buffer` メッセージング ブロックにメッセージを同期的に渡します。  このメソッドは、ソース ブロックから呼び出されたときに `send` メソッドによって呼び出されます。|  
|[overwrite\_buffer::supports\_anonymous\_source メソッド](../Topic/overwrite_buffer::supports_anonymous_source%20Method.md)|`supports_anonymous_source` のメソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け取ることができることを示すためにオーバーライドします。オーバーライド \([ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\)。|  
  
## 解説  
 `overwrite_buffer` メッセージング ブロックは、そこに格納されているメッセージのコピーを個々のターゲットに反映します。  
  
 詳細については、「[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
## 継承階層  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `overwrite_buffer`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [unbounded\_buffer クラス](../Topic/unbounded_buffer%20Class.md)   
 [single\_assignment クラス](../../../parallel/concrt/reference/single-assignment-class.md)