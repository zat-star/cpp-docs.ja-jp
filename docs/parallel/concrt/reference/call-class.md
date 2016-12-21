---
title: "call クラス | Microsoft Docs"
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
  - "agents/concurrency::call"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call クラス"
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# call クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`call` メッセージング ブロックは、複数のソースを持つ、順序付けられた `target_block` であり、メッセージを受け取ったときに指定された関数を呼び出します。  
  
## 構文  
  
```  
template<  
   class _Type,  
   class _FunctorType = std::tr1::function<void(_Type const&)>  
>  
class call : public target_block<multi_link_registry<ISource<_Type>>>;  
```  
  
#### パラメーター  
 `_Type`  
 このブロックに伝達されるメッセージのペイロード型。  
  
 `_FunctorType`  
 このブロックが受け取ることができる関数のシグネチャ。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[call::call コンストラクター](../Topic/call::call%20Constructor.md)|オーバーロードされます。  `call` メッセージング ブロックを構築します。|  
|[call::~call デストラクター](../Topic/call::~call%20Destructor.md)|`call` メッセージング ブロックを破棄します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[call::process\_input\_messages メソッド](../Topic/call::process_input_messages%20Method.md)|入力メッセージでの関数の呼び出しを実行します。|  
|[call::process\_message メソッド](../Topic/call::process_message%20Method.md)|この `call` メッセージング ブロックで受け取られたメッセージを処理します。|  
|[call::propagate\_message メソッド](../Topic/call::propagate_message%20Method.md)|`ISource` ブロックからこの `call` メッセージング ブロックにメッセージを非同期に渡します。  このメソッドは、ソース ブロックから呼び出されたときに `propagate` メソッドによって呼び出されます。|  
|[call::send\_message メソッド](../Topic/call::send_message%20Method.md)|`ISource` ブロックからこの `call` メッセージング ブロックにメッセージを同期的に渡します。  このメソッドは、ソース ブロックから呼び出されたときに `send` メソッドによって呼び出されます。|  
|[call::supports\_anonymous\_source メソッド](../Topic/call::supports_anonymous_source%20Method.md)|`supports_anonymous_source` のメソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け取ることができることを示すためにオーバーライドします。オーバーライド \([ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\)。|  
  
## 解説  
 詳細については、「[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
## 継承階層  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [target\_block](../../../parallel/concrt/reference/target-block-class.md)  
  
 `call`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [transformer クラス](../../../parallel/concrt/reference/transformer-class.md)