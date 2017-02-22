---
title: "invalid_compute_domain クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::invalid_compute_domain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_compute_domain クラス"
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# invalid_compute_domain クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

ランタイムが指定された [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) の呼び出しサイトの計算のドメインを使用してカーネルを開始できない場合にスローされる例外。  
  
## 構文  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[invalid\_compute\_domain::invalid\_compute\_domain コンストラクター](../Topic/invalid_compute_domain::invalid_compute_domain%20Constructor.md)|`invalid_compute_domain` クラスの新しいインスタンスを初期化します。|  
  
## 継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## 必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)