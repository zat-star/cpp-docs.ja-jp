---
title: "recursive_timed_mutex クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::recursive_timed_mutex"
dev_langs: 
  - "C++"
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# recursive_timed_mutex クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*指定されたミューテックスの種類を*表します。  プログラム内のタイム限られたブロッキングを使用してこの型のオブジェクトが相互排他を適用するために使用されます。  型 [timed\_mutex](../standard-library/timed-mutex-class.md)オブジェクトとは異なり、`recursive_timed_mutex` オブジェクトのロック メソッドを呼び出した場合は、明示されています。  
  
## 構文  
  
```  
class recursive_timed_mutex;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[recursive\_timed\_mutex::recursive\_timed\_mutex コンストラクター](../Topic/recursive_timed_mutex::recursive_timed_mutex%20Constructor.md)|ロックされていない `recursive_timed_mutex` オブジェクトを構築します。|  
|[recursive\_timed\_mutex::~recursive\_timed\_mutex デストラクター](../Topic/recursive_timed_mutex::~recursive_timed_mutex%20Destructor.md)|`recursive_timed_mutex` オブジェクトで使用されているリソースを解放します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[recursive\_timed\_mutex::lock メソッド](../Topic/recursive_timed_mutex::lock%20Method.md)|呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。|  
|[recursive\_timed\_mutex::try\_lock メソッド](../Topic/recursive_timed_mutex::try_lock%20Method.md)|ブロックせずに `mutex` の所有権を取得しようとします。|  
|[recursive\_timed\_mutex::try\_lock\_for メソッド](../Topic/recursive_timed_mutex::try_lock_for%20Method.md)|指定された間隔の `mutex` の所有権を取得しようとします。|  
|[recursive\_timed\_mutex::try\_lock\_until メソッド](../Topic/recursive_timed_mutex::try_lock_until%20Method.md)|指定した時間の `mutex` の所有権を取得しようとします。|  
|[recursive\_timed\_mutex::unlock メソッド](../Topic/recursive_timed_mutex::unlock%20Method.md)|`mutex` の所有権を解放します。|  
  
## 必要条件  
 **ヘッダー:** mutex  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)