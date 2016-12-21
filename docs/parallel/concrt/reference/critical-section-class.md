---
title: "critical_section クラス | Microsoft Docs"
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
  - "concrt/concurrency::critical_section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "critical_section クラス"
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
caps.latest.revision: 23
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# critical_section クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

同時実行ランタイムを明示的に認識する再入不可能なミューテックスです。  
  
## 構文  
  
```  
class critical_section;  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`native_handle_type`|`critical_section` オブジェクトへの参照。|  
  
### パブリック クラス  
  
|名前|説明|  
|--------|--------|  
|[critical\_section::scoped\_lock クラス](../Topic/critical_section::scoped_lock%20Class.md)|`critical_section` オブジェクトの例外セーフ RAII ラッパー。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[critical\_section::critical\_section コンストラクター](../Topic/critical_section::critical_section%20Constructor.md)|新しいクリティカル セクションを構築します。|  
|[critical\_section::~critical\_section デストラクター](../Topic/critical_section::~critical_section%20Destructor.md)|クリティカル セクションを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[critical\_section::lock メソッド](../Topic/critical_section::lock%20Method.md)|このクリティカル セクションを取得します。|  
|[critical\_section::native\_handle メソッド](../Topic/critical_section::native_handle%20Method.md)|プラットフォーム固有のネイティブ ハンドル \(存在する場合\) を返します。|  
|[critical\_section::try\_lock メソッド](../Topic/critical_section::try_lock%20Method.md)|ブロックせずにロックを取得することを試みます。|  
|[critical\_section::try\_lock\_for メソッド](../Topic/critical_section::try_lock_for%20Method.md)|特定の時間をミリ秒単位でブロックせずにロックを取得することを試みます。|  
|[critical\_section::unlock メソッド](../Topic/critical_section::unlock%20Method.md)|クリティカル セクションのロックを解除します。|  
  
## 解説  
 詳細については、「[同期データ構造](../Topic/Synchronization%20Data%20Structures.md)」を参照してください。  
  
## 継承階層  
 `critical_section`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [reader\_writer\_lock クラス](../Topic/reader_writer_lock%20Class.md)