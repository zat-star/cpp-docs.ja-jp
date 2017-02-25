---
title: "timed_mutex クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::timed_mutex"
dev_langs: 
  - "C++"
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# timed_mutex クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*指定されたミューテックスの種類を*表します。  この型のオブジェクトは、プログラム内でのタイム、ブロッキングと相互排他を適用するために使用されます。  
  
## 構文  
  
```  
class timed_mutex;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[timed\_mutex::timed\_mutex コンストラクター](../Topic/timed_mutex::timed_mutex%20Constructor.md)|ロックされていない `timed_mutex` オブジェクトを構築します。|  
|[timed\_mutex::~timed\_mutex デストラクター](../Topic/timed_mutex::~timed_mutex%20Destructor.md)|`timed_mutex` オブジェクトで使用されているリソースを解放します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[timed\_mutex::lock メソッド](../Topic/timed_mutex::lock%20Method.md)|呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。|  
|[timed\_mutex::try\_lock メソッド](../Topic/timed_mutex::try_lock%20Method.md)|ブロックせずに `mutex` の所有権を取得しようとします。|  
|[timed\_mutex::try\_lock\_for メソッド](../Topic/timed_mutex::try_lock_for%20Method.md)|指定された間隔の `mutex` の所有権を取得しようとします。|  
|[timed\_mutex::try\_lock\_until メソッド](../Topic/timed_mutex::try_lock_until%20Method.md)|指定した時間の `mutex` の所有権を取得しようとします。|  
|[timed\_mutex::unlock メソッド](../Topic/timed_mutex::unlock%20Method.md)|`mutex` の所有権を解放します。|  
  
## 必要条件  
 **ヘッダー:** mutex  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)