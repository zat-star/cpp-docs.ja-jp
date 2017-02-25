---
title: "operation_timed_out クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::operation_timed_out"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operation_timed_out クラス"
ms.assetid: 963efe1d-a6e0-477c-9a70-d93d8412c897
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# operation_timed_out クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、操作がタイムアウトした場合にスローされる例外を表します。  
  
## 構文  
  
```  
class operation_timed_out : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[operation\_timed\_out::operation\_timed\_out コンストラクター](../Topic/operation_timed_out::operation_timed_out%20Constructor.md)|オーバーロードされます。  `operation_timed_out` オブジェクトを構築します。|  
  
## 継承階層  
 `exception`  
  
 `operation_timed_out`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)