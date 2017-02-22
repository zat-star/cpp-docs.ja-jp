---
title: "scheduler_resource_allocation_error クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::scheduler_resource_allocation_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_resource_allocation_error クラス"
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# scheduler_resource_allocation_error クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、同時実行ランタイムでクリティカル リソースを取得できないためにスローされる例外を表します。  
  
## 構文  
  
```  
class scheduler_resource_allocation_error : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[scheduler\_resource\_allocation\_error::scheduler\_resource\_allocation\_error コンストラクター](../Topic/scheduler_resource_allocation_error::scheduler_resource_allocation_error%20Constructor.md)|オーバーロードされます。  `scheduler_resource_allocation_error` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[scheduler\_resource\_allocation\_error::get\_error\_code メソッド](../Topic/scheduler_resource_allocation_error::get_error_code%20Method.md)|例外の原因となったエラー コードを返します。|  
  
## 解説  
 通常、この例外は、同時実行ランタイム内からのオペレーティング システムの呼び出しが失敗した場合にスローされます。  呼び出しから Win32 メソッドに、`GetLastError` 返されるエラー コードは `HRESULT` 型の値に変換され、`get_error_code` のメソッドを使用して取得することもできます。  
  
## 継承階層  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)