---
title: "message_not_found クラス | Microsoft Docs"
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
  - "concrt/concurrency::message_not_found"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message_not_found クラス"
ms.assetid: a96b9995-5ad7-4600-83c8-c15e329ff10e
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# message_not_found クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、要求されたメッセージがメッセージング ブロックで見つからない場合にスローされる例外を表します。  
  
## 構文  
  
```  
class message_not_found : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[message\_not\_found::message\_not\_found コンストラクター](../Topic/message_not_found::message_not_found%20Constructor.md)|オーバーロードされます。  `message_not_found` オブジェクトを構築します。|  
  
## 継承階層  
 `exception`  
  
 `message_not_found`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)