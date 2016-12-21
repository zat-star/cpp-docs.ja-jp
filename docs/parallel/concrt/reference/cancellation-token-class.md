---
title: "cancellation_token クラス | Microsoft Docs"
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
  - "pplcancellation_token/concurrency::cancellation_token"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token クラス"
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# cancellation_token クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`cancellation_token` クラスは、ある操作の取り消しが要求されたかどうかを判断する機能を表します。  特定のトークンを `task_group`、`structured_task_group`、または `task` に関連付けると、暗黙的な取り消しを指定できます。  関連付けられた `cancellation_token_source` が取り消されたときに、取り消すためにポーリングしたり、コールバックを登録したりすることもできます。  
  
## 構文  
  
```  
class cancellation_token;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[cancellation\_token::cancellation\_token コンストラクター](../Topic/cancellation_token::cancellation_token%20Constructor.md)||  
|[cancellation\_token::~cancellation\_token デストラクター](../Topic/cancellation_token::~cancellation_token%20Destructor.md)||  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[cancellation\_token::deregister\_callback メソッド](../Topic/cancellation_token::deregister_callback%20Method.md)|登録時に返された `cancellation_token_registration` オブジェクトに基づく `register` メソッドによって以前に登録されたコールバックを削除します。|  
|[cancellation\_token::is\_cancelable メソッド](../Topic/cancellation_token::is_cancelable%20Method.md)|このトークンを取り消すことができるかどうかを示す値を返します。|  
|[cancellation\_token::is\_canceled メソッド](../Topic/cancellation_token::is_canceled%20Method.md)|トークンが取り消された場合は `true` を返します。|  
|[cancellation\_token::none メソッド](../Topic/cancellation_token::none%20Method.md)|取り消しの対象とはならないキャンセル トークンを返します。|  
|[cancellation\_token::register\_callback メソッド](../Topic/cancellation_token::register_callback%20Method.md)|コールバック関数をトークンに登録します。  トークンが取り消された場合、コールバックが行われます。  このメソッドが呼び出された時点で既にコールバックが取り消されている場合、コールバックは即座に同期的に行われることに注意してください。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[cancellation\_token::operator\!\= 演算子](../Topic/cancellation_token::operator!=%20Operator.md)||  
|[cancellation\_token::operator\= 演算子](../Topic/cancellation_token::operator=%20Operator.md)||  
|[cancellation\_token::operator\=\= 演算子](../Topic/cancellation_token::operator==%20Operator.md)||  
  
## 継承階層  
 `cancellation_token`  
  
## 必要条件  
 **ヘッダー:** pplcancellation\_token.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)