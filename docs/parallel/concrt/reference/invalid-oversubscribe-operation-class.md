---
title: "invalid_oversubscribe_operation クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_oversubscribe_operation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_oversubscribe_operation クラス"
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_oversubscribe_operation クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`_BeginOversubscription` パラメーターが `true` に設定された `Context::Oversubscribe` メソッドを事前に呼び出さずに、`_BeginOversubscription` パラメーターが `false` に設定された `Context::Oversubscribe` メソッドを呼び出した場合にスローされる例外を表します。  
  
## 構文  
  
```  
class invalid_oversubscribe_operation : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[invalid\_oversubscribe\_operation::invalid\_oversubscribe\_operation コンストラクター](../Topic/invalid_oversubscribe_operation::invalid_oversubscribe_operation%20Constructor.md)|オーバーロードされます。  `invalid_oversubscribe_operation` オブジェクトを構築します。|  
  
## 継承階層  
 `exception`  
  
 `invalid_oversubscribe_operation`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Context::Oversubscribe メソッド](../Topic/Context::Oversubscribe%20Method.md)