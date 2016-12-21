---
title: "improper_lock クラス | Microsoft Docs"
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
  - "concrt/concurrency::improper_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_lock クラス"
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# improper_lock クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、ロックが正しく取得されなかった場合にスローされる例外を表します。  
  
## 構文  
  
```  
class improper_lock : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[improper\_lock::improper\_lock コンストラクター](../Topic/improper_lock::improper_lock%20Constructor.md)|オーバーロードされます。  `improper_lock exception` を構築します。|  
  
## 解説  
 通常、この例外は、同じコンテキストで再入不可能なロックを再帰的に取得しようとしたときにスローされます。  
  
## 継承階層  
 `exception`  
  
 `improper_lock`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [critical\_section クラス](../../../parallel/concrt/reference/critical-section-class.md)   
 [reader\_writer\_lock クラス](../Topic/reader_writer_lock%20Class.md)