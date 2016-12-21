---
title: "cancellation_token_source クラス | Microsoft Docs"
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
  - "pplcancellation_token/concurrency::cancellation_token_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_source クラス"
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# cancellation_token_source クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`cancellation_token_source` クラスは、取り消し可能な操作を取り消す機能を表します。  
  
## 構文  
  
```  
class cancellation_token_source;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[cancellation\_token\_source::cancellation\_token\_source コンストラクター](../Topic/cancellation_token_source::cancellation_token_source%20Constructor.md)|オーバーロードされます。  新しい `cancellation_token_source` を構築します。  ソースを使用して、一部の取り消し可能な操作について取り消しのフラグを設定できます。|  
|[cancellation\_token\_source::~cancellation\_token\_source デストラクター](../Topic/cancellation_token_source::~cancellation_token_source%20Destructor.md)||  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[cancellation\_token\_source::cancel メソッド](../Topic/cancellation_token_source::cancel%20Method.md)|トークンを取り消します。  トークンを利用するすべての `task_group`、`structured_task_group`、および `task` は、このメソッドが呼び出されたときに取り消され、次の割り込みポイントで例外がスローされます。|  
|[cancellation\_token\_source::create\_linked\_source メソッド](../Topic/cancellation_token_source::create_linked_source%20Method.md)|オーバーロードされます。  指定されたトークンが取り消されたときに取り消される `cancellation_token_source` を作成します。|  
|[cancellation\_token\_source::get\_token メソッド](../Topic/cancellation_token_source::get_token%20Method.md)|このソースに関連付けられたキャンセル トークンを返します。  返されたトークンは、取り消すためにポーリングしたり、取り消しが発生した場合にコールバックを指定したりできます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[cancellation\_token\_source::operator\!\= 演算子](../Topic/cancellation_token_source::operator!=%20Operator.md)||  
|[cancellation\_token\_source::operator\= 演算子](../Topic/cancellation_token_source::operator=%20Operator.md)||  
|[cancellation\_token\_source::operator\=\= 演算子](../Topic/cancellation_token_source::operator==%20Operator.md)||  
  
## 継承階層  
 `cancellation_token_source`  
  
## 必要条件  
 **ヘッダー:** pplcancellation\_token.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)