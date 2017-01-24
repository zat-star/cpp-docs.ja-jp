---
title: "cancellation_token_registration クラス | Microsoft Docs"
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
  - "pplcancellation_token/concurrency::cancellation_token_registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_registration クラス"
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# cancellation_token_registration クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`cancellation_token_registration` クラスは、`cancellation_token` からのコールバック通知を表します。  `cancellation_token` の `register` メソッドを使用して取り消し発生の通知を受け取るとき、`cancellation_token_registration` オブジェクトはハンドルとしてコールバックに返されます。したがって、呼び出し元は `deregister` メソッドを使用して、特定のコールバックが以降行われないように要求できます。  
  
## 構文  
  
```  
class cancellation_token_registration;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[cancellation\_token\_registration::cancellation\_token\_registration コンストラクター](../Topic/cancellation_token_registration::cancellation_token_registration%20Constructor.md)||  
|[cancellation\_token\_registration::~cancellation\_token\_registration デストラクター](../Topic/cancellation_token_registration::~cancellation_token_registration%20Destructor.md)||  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[cancellation\_token\_registration::operator\!\= 演算子](../Topic/cancellation_token_registration::operator!=%20Operator.md)||  
|[cancellation\_token\_registration::operator\= 演算子](../Topic/cancellation_token_registration::operator=%20Operator.md)||  
|[cancellation\_token\_registration::operator\=\= 演算子](../Topic/cancellation_token_registration::operator==%20Operator.md)||  
  
## 継承階層  
 `cancellation_token_registration`  
  
## 必要条件  
 **ヘッダー:** pplcancellation\_token.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)