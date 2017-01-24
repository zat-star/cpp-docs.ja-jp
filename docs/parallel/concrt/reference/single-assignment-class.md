---
title: "single_assignment クラス | Microsoft Docs"
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
  - "agents/concurrency::single_assignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single_assignment クラス"
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# single_assignment クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`single_assignment` メッセージング ブロックは、一度だけ書き込むことができる `message` を 1 つ格納できる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。  
  
## 構文  
  
```  
template<  
   class _Type  
>  
class single_assignment : public propagator_block<multi_link_registry<ITarget<_Type>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### パラメーター  
 `_Type`  
 バッファーによって格納および伝達されるメッセージのペイロード型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[single\_assignment::single\_assignment コンストラクター](../Topic/single_assignment::single_assignment%20Constructor.md)|オーバーロードされます。  `single_assignment` メッセージング ブロックを構築します。|  
|[single\_assignment::~single\_assignment デストラクター](../Topic/single_assignment::~single_assignment%20Destructor.md)|`single_assignment` メッセージング ブロックを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[single\_assignment::has\_value メソッド](../Topic/single_assignment::has_value%20Method.md)|この `single_assignment` メッセージング ブロックが値で初期化されているかどうかをチェックします。|  
|[single\_assignment::value メソッド](../Topic/single_assignment::value%20Method.md)|`single_assignment` メッセージング ブロックに格納されるメッセージの現在のペイロードへの参照を取得します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[single\_assignment::accept\_message メソッド](../Topic/single_assignment::accept_message%20Method.md)|この `single_assignment` メッセージング ブロックによって提供されたメッセージを受け入れ、そのメッセージのコピーを呼び出し元に返します。|  
|[single\_assignment::consume\_message メソッド](../Topic/single_assignment::consume_message%20Method.md)|この `single_assignment` によって以前に提供され、ターゲットによって予約されたメッセージを使用して、そのメッセージのコピーを呼び出し元に返します。|  
|[single\_assignment::link\_target\_notification メソッド](../Topic/single_assignment::link_target_notification%20Method.md)|新しいターゲットがこの `single_assignment` メッセージング ブロックにリンクされたことを通知するコールバックです。|  
|[single\_assignment::propagate\_message メソッド](../Topic/single_assignment::propagate_message%20Method.md)|`ISource` ブロックからこの `single_assignment` メッセージング ブロックにメッセージを非同期に渡します。  このメソッドは、ソース ブロックから呼び出されたときに `propagate` メソッドによって呼び出されます。|  
|[single\_assignment::propagate\_to\_any\_targets メソッド](../Topic/single_assignment::propagate_to_any_targets%20Method.md)|`message` `_PMessage` をこの `single_assignment` メッセージング ブロックに配置し、それをリンクされたすべてのターゲットに提供します。|  
|[single\_assignment::release\_message メソッド](../Topic/single_assignment::release_message%20Method.md)|以前に行われたメッセージの予約を解放します。\([source\_block::release\_message](../Topic/source_block::release_message%20Method.md) をオーバーライドします。\)|  
|[single\_assignment::reserve\_message メソッド](../Topic/single_assignment::reserve_message%20Method.md)|この `single_assignment` メッセージング ブロックによって以前に提供されたメッセージを予約します。\([source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md) をオーバーライドします。\)|  
|[single\_assignment::resume\_propagation メソッド](../Topic/single_assignment::resume_propagation%20Method.md)|予約が解放された後で反映を再開します。\([source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md) をオーバーライドします。\)|  
|[single\_assignment::send\_message メソッド](../Topic/single_assignment::send_message%20Method.md)|`ISource` ブロックからこの `single_assignment` メッセージング ブロックにメッセージを同期的に渡します。  このメソッドは、ソース ブロックから呼び出されたときに `send` メソッドによって呼び出されます。|  
  
## 解説  
 `single_assignment` メッセージング ブロックは、そこに格納されているメッセージのコピーを個々のターゲットに送信します。  
  
 詳細については、「[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
## 継承階層  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `single_assignment`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [overwrite\_buffer クラス](../../../parallel/concrt/reference/overwrite-buffer-class.md)   
 [unbounded\_buffer クラス](../Topic/unbounded_buffer%20Class.md)