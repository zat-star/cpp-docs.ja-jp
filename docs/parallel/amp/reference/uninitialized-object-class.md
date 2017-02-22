---
title: "uninitialized_object クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::uninitialized_object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uninitialized_object クラス"
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# uninitialized_object クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

初期化されていないオブジェクトが使用される場合にスローされる例外です。  
  
## 構文  
  
```  
class uninitialized_object : public runtime_exception;  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[uninitialized\_object::uninitialized\_object コンストラクター](../Topic/uninitialized_object::uninitialized_object%20Constructor.md)|`uninitialized_object` クラスの新しいインスタンスを初期化します。|  
  
## 継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `uninitialized_object`  
  
## 必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)