---
title: "out_of_memory クラス | Microsoft Docs"
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
  - "amprt/Concurrency::out_of_memory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out_of_memory クラス"
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# out_of_memory クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

システムまたはデバイスのメモリ不足のためにメソッドが失敗した場合にスローされる例外。  
  
## 構文  
  
```  
class out_of_memory : public runtime_exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[out\_of\_memory::out\_of\_memory コンストラクター](../Topic/out_of_memory::out_of_memory%20Constructor.md)|`out_of_memory` クラスの新しいインスタンスを初期化します。|  
  
## 継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## 必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)