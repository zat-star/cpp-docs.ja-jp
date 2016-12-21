---
title: "unique_lock クラス | Microsoft Docs"
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
  - "mutex/std::unique_lock"
dev_langs: 
  - "C++"
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
caps.latest.revision: 10
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unique_lock クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`mutex`のロックとロック解除を管理するオブジェクトを作成するにインスタンス化することができるテンプレートを表します。  
  
## 構文  
  
```  
template<class Mutex>  
class unique_lock;  
```  
  
## 解説  
 テンプレート引数 `Mutex` は *ミューテックスの型に名前を*付ける必要があります。  
  
 内部的には、`unique_lock` を示す `bool` と `mutex` 関連のオブジェクトには、現在のスレッドが `mutex`を所有するかどうかのポインターを格納します。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`unique_lock::mutex_type`|テンプレート引数 `Mutex`のシノニムです。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[unique\_lock::unique\_lock コンストラクター](../Topic/unique_lock::unique_lock%20Constructor.md)|`unique_lock` オブジェクトを構築します。|  
|[unique\_lock::~unique\_lock デストラクター](../Topic/unique_lock::~unique_lock%20Destructor.md)|`unique_lock` オブジェクトに関連付けられたリソースを解放します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[unique\_lock::lock メソッド](../Topic/unique_lock::lock%20Method.md)|スレッドが関連する `mutex`の所有権を取得するまで呼び出し元スレッドをブロックします。|  
|[unique\_lock::mutex メソッド](../Topic/unique_lock::mutex%20Method.md)|関連する `mutex`に保存されたポインターを取得します。|  
|[unique\_lock::owns\_lock メソッド](../Topic/unique_lock::owns_lock%20Method.md)|呼び出し元スレッドが関連する `mutex`を所有するかどうかを指定します。|  
|[unique\_lock::release メソッド](../Topic/unique_lock::release%20Method.md)|`mutex` 関連のオブジェクトから `unique_lock` オブジェクトの関連付けを解除し。|  
|[unique\_lock::swap メソッド](../Topic/unique_lock::swap%20Method.md)|指定されたオブジェクトの型に関連付けられた `mutex` および所有権の状態を交換します。|  
|[unique\_lock::try\_lock メソッド](../Topic/unique_lock::try_lock%20Method.md)|ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。|  
|[unique\_lock::try\_lock\_for メソッド](../Topic/unique_lock::try_lock_for%20Method.md)|ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。|  
|[unique\_lock::try\_lock\_until メソッド](../Topic/unique_lock::try_lock_until%20Method.md)|ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。|  
|[unique\_lock::unlock メソッド](../Topic/unique_lock::unlock%20Method.md)|関連する `mutex`の所有権を解放します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[unique\_lock::operator bool 演算子](../Topic/unique_lock::operator%20bool%20Operator.md)|呼び出し元のスレッドに関連付けられた `mutex`の所有権を持つかどうかを指定します。|  
|[unique\_lock::operator\= 演算子](../Topic/unique_lock::operator=%20Operator.md)|指定されたオブジェクトの `mutex` の格納されたポインターと関連の所有権の状態をコピーします。|  
  
## 継承階層  
 `unique_lock`  
  
## 必要条件  
 **ヘッダー:** mutex  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)