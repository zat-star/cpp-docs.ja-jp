---
title: "propagator_block クラス | Microsoft Docs"
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
  - "agents/concurrency::propagator_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propagator_block クラス"
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# propagator_block クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`propagator_block` クラスは、ソースでもありターゲットでもあるメッセージ ブロックの抽象基底クラスです。  `source_block` クラスと `target_block` クラスの両方の機能が組み合わされています。  
  
## 構文  
  
```  
template<  
   class _TargetLinkRegistry,  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>  
>  
class propagator_block : public source_block<_TargetLinkRegistry, _MessageProcessorType>, public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### パラメーター  
 `_TargetLinkRegistry`  
 ターゲット リンクの保持に使用されるリンク レジストリ。  
  
 `_SourceLinkRegistry`  
 ソース リンクの保持に使用されるリンク レジストリ。  
  
 `_MessageProcessorType`  
 メッセージを処理するプロセッサの種類。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`source_iterator`|この `propagator_block` に対する `source_link_manager` の反復子の型。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[propagator\_block::propagator\_block コンストラクター](../Topic/propagator_block::propagator_block%20Constructor.md)|`propagator_block` オブジェクトを構築します。|  
|[propagator\_block::~propagator\_block デストラクター](../Topic/propagator_block::~propagator_block%20Destructor.md)|`propagator_block` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[propagator\_block::propagate メソッド](../Topic/propagator_block::propagate%20Method.md)|ソース ブロックからこのターゲット ブロックにメッセージを非同期的に渡します。|  
|[propagator\_block::send メソッド](../Topic/propagator_block::send%20Method.md)|このブロックへのメッセージを同期的に開始します。  `ISource` ブロックによって呼び出されます。  この関数が完了すると、このブロックには既にメッセージが反映されています。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[propagator\_block::decline\_incoming\_messages メソッド](../Topic/propagator_block::decline_incoming_messages%20Method.md)|新しいメッセージが拒否されるブロックを指定します。|  
|[propagator\_block::initialize\_source\_and\_target メソッド](../Topic/propagator_block::initialize_source_and_target%20Method.md)|ベース オブジェクトを初期化します。  特に、`message_processor` オブジェクトは初期化する必要があります。|  
|[propagator\_block::link\_source メソッド](../Topic/propagator_block::link_source%20Method.md)|指定されたソース ブロックをこの `propagator_block` オブジェクトにリンクします。|  
|[propagator\_block::process\_input\_messages メソッド](../Topic/propagator_block::process_input_messages%20Method.md)|プロセス入力メッセージ。  これは、source\_block \(オーバーライド [source\_block::process\_input\_messages](../Topic/source_block::process_input_messages%20Method.md)\) から派生する伝達子ブロックの場合にのみ有効です|  
|[propagator\_block::propagate\_message メソッド](../Topic/propagator_block::propagate_message%20Method.md)|派生クラスでオーバーライドされると、このメソッドは `ISource` ブロックからこの `propagator_block` オブジェクトに非同期的にメッセージを渡します。  このメソッドは、ソース ブロックから呼び出されたときに `propagate` メソッドによって呼び出されます。|  
|[propagator\_block::register\_filter メソッド](../Topic/propagator_block::register_filter%20Method.md)|すべての受信メッセージに対して呼び出されるフィルター メソッドを登録します。|  
|[propagator\_block::remove\_network\_links メソッド](../Topic/propagator_block::remove_network_links%20Method.md)|この `propagator_block` オブジェクトからすべてのソース ネットワーク リンクとターゲット ネットワーク リンクを削除します。|  
|[propagator\_block::send\_message メソッド](../Topic/propagator_block::send_message%20Method.md)|派生クラスでオーバーライドされると、このメソッドは `ISource` ブロックからこの `propagator_block` オブジェクトに同期的にメッセージを渡します。  このメソッドは、ソース ブロックから呼び出されたときに `send` メソッドによって呼び出されます。|  
|[propagator\_block::unlink\_source メソッド](../Topic/propagator_block::unlink_source%20Method.md)|指定されたソース ブロックとこの `propagator_block` オブジェクトとのリンクを解除します。|  
|[propagator\_block::unlink\_sources メソッド](../Topic/propagator_block::unlink_sources%20Method.md)|この `propagator_block` オブジェクトからすべてのソース ブロックのリンクを解除します。\([ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md) をオーバーライドします\)。|  
  
## 解説  
 多重継承を回避するために、`propagator_block` クラスは `source_block` クラスおよび `ITarget` 抽象クラスから継承します。  `target_block` クラスのほとんどの機能はここでレプリケートされます。  
  
## 継承階層  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 `propagator_block`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [source\_block クラス](../Topic/source_block%20Class.md)   
 [ITarget クラス](../../../parallel/concrt/reference/itarget-class.md)