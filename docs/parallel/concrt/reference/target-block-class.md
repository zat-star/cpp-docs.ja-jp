---
title: "target_block クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::target_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "target_block クラス"
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# target_block クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`target_block` クラスは、基本的なリンク管理機能と、ターゲットのみのブロックのエラー チェック機能を実現する抽象基底クラスです。  
  
## 構文  
  
```  
template<  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>  
>  
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### パラメーター  
 `_SourceLinkRegistry`  
 ソース リンクの保持に使用されるリンク レジストリ。  
  
 `_MessageProcessorType`  
 メッセージを処理するプロセッサの種類。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`source_iterator`|この `target_block` オブジェクトに対する `source_link_manager` の反復子の種類。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[target\_block::target\_block コンストラクター](../Topic/target_block::target_block%20Constructor.md)|`target_block` オブジェクトを構築します。|  
|[target\_block::~target\_block デストラクター](../Topic/target_block::~target_block%20Destructor.md)|`target_block` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[target\_block::propagate メソッド](../Topic/target_block::propagate%20Method.md)|ソース ブロックからこのターゲット ブロックにメッセージを非同期的に渡します。|  
|[target\_block::send メソッド](../Topic/target_block::send%20Method.md)|ソース ブロックからこのターゲット ブロックにメッセージを同期的に渡します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[target\_block::async\_send メソッド](../Topic/target_block::async_send%20Method.md)|処理のためにメッセージを非同期的に送信します。|  
|[target\_block::decline\_incoming\_messages メソッド](../Topic/target_block::decline_incoming_messages%20Method.md)|新しいメッセージが拒否されるブロックを指定します。|  
|[target\_block::enable\_batched\_processing メソッド](../Topic/target_block::enable_batched_processing%20Method.md)|このブロックのバッチ プロセッシングを有効にします。|  
|[target\_block::initialize\_target メソッド](../Topic/target_block::initialize_target%20Method.md)|ベース オブジェクトを初期化します。  特に、`message_processor` オブジェクトは初期化する必要があります。|  
|[target\_block::link\_source メソッド](../Topic/target_block::link_source%20Method.md)|指定されたソース ブロックをこの `target_block` オブジェクトにリンクします。|  
|[target\_block::process\_input\_messages メソッド](../Topic/target_block::process_input_messages%20Method.md)|入力として受け取るメッセージを処理します。|  
|[target\_block::process\_message メソッド](../Topic/target_block::process_message%20Method.md)|派生クラスでオーバーライドされた場合、プロセス `target_block` オブジェクトで受け取られたメッセージを処理します。|  
|[target\_block::propagate\_message メソッド](../Topic/target_block::propagate_message%20Method.md)|派生クラスでオーバーライドされると、このメソッドは `ISource` ブロックからこの `target_block` オブジェクトに非同期的にメッセージを渡します。  このメソッドは、ソース ブロックから呼び出されたときに `propagate` メソッドによって呼び出されます。|  
|[target\_block::register\_filter メソッド](../Topic/target_block::register_filter%20Method.md)|すべての受信メッセージに対して呼び出されるフィルター メソッドを登録します。|  
|[target\_block::remove\_sources メソッド](../Topic/target_block::remove_sources%20Method.md)|未処理の非同期送信操作が完了するのを待ってから、すべてのソースのリンクを解除します。|  
|[target\_block::send\_message メソッド](../Topic/target_block::send_message%20Method.md)|派生クラスでオーバーライドされると、このメソッドは `ISource` ブロックからこの `target_block` オブジェクトに同期的にメッセージを渡します。  このメソッドは、ソース ブロックから呼び出されたときに `send` メソッドによって呼び出されます。|  
|[target\_block::sync\_send メソッド](../Topic/target_block::sync_send%20Method.md)|処理のためにメッセージを同期的に送信します。|  
|[target\_block::unlink\_source メソッド](../Topic/target_block::unlink_source%20Method.md)|指定されたソース ブロックとこの `target_block` オブジェクトとのリンクを解除します。|  
|[target\_block::unlink\_sources メソッド](../Topic/target_block::unlink_sources%20Method.md)|この `target_block` オブジェクトからすべてのソース ブロックのリンクを解除します。\([ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md) をオーバーライドします\)。|  
|[target\_block::wait\_for\_async\_sends メソッド](../Topic/target_block::wait_for_async_sends%20Method.md)|すべての非同期伝達が完了するまで待機します。|  
  
## 継承階層  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 `target_block`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ITarget クラス](../../../parallel/concrt/reference/itarget-class.md)