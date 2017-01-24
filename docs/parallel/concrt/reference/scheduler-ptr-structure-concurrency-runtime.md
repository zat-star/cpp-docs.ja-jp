---
title: "scheduler_ptr 構造体 (同時実行ランタイム) | Microsoft Docs"
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
  - "pplinterface/concurrency::scheduler_ptr"
dev_langs: 
  - "C++"
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# scheduler_ptr 構造体 (同時実行ランタイム)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

スケジューラへのポインターを表します。  このクラスによって、shared\_ptr を使用して共有有効期間を指定できるように、または、生ポインターを使用して参照できるようにします。  
  
## 構文  
  
```  
struct scheduler_ptr;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[scheduler\_ptr::scheduler\_ptr コンストラクター \(同時実行ランタイム\)](../Topic/scheduler_ptr::scheduler_ptr%20Constructor%20\(Concurrency%20Runtime\).md)|オーバーロードされます。  shared\_ptr からスケジューラを指すスケジューラ ポインターを作成します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[scheduler\_ptr::get メソッド \(同時実行ランタイム\)](../Topic/scheduler_ptr::get%20Method%20\(Concurrency%20Runtime\).md)|スケジューラへの生のポインターを返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[scheduler\_ptr::operator bool 演算子 \(同時実行ランタイム\)](../Topic/scheduler_ptr::operator%20bool%20Operator%20\(Concurrency%20Runtime\).md)|スケジューラ ポインターが null 以外であるかどうかをテストします。|  
|[scheduler\_ptr::operator\-\> 演算子 \(同時実行ランタイム\)](../Topic/scheduler_ptr::operator-%3E%20Operator%20\(Concurrency%20Runtime\).md)|ポインターのように動作します。|  
  
## 継承階層  
 `scheduler_ptr`  
  
## 必要条件  
 **ヘッダー:** pplinterface.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)