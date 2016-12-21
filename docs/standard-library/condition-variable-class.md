---
title: "condition_variable クラス | Microsoft Docs"
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
  - "condition_variable/std::condition_variable"
dev_langs: 
  - "C++"
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: 16
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# condition_variable クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`unique_lock<mutex>` 型の `mutex` がある場合に、イベントを待機するために `condition_variable` クラスを使用します。  この型のオブジェクトは [condition\_variable\_any\<unique\_lock\<mutex\>\>](../standard-library/condition-variable-any-class.md) 型のオブジェクトより優れたパフォーマンスを実現することがあります。  
  
## 構文  
  
```  
class condition_variable;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[condition\_variable::condition\_variable コンストラクター](../Topic/condition_variable::condition_variable%20Constructor.md)|`condition_variable` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[condition\_variable::native\_handle メソッド](../Topic/condition_variable::native_handle%20Method.md)|condition\_variable ハンドルを表す実装固有の型を返します。|  
|[condition\_variable::notify\_all メソッド](../Topic/condition_variable::notify_all%20Method.md)|`condition_variable` オブジェクトを待機しているすべてのスレッドのブロックを解除します。|  
|[condition\_variable::notify\_one メソッド](../Topic/condition_variable::notify_one%20Method.md)|`condition_variable` オブジェクトを待機しているスレッドの 1 つのブロックを解除します。|  
|[condition\_variable::wait メソッド](../Topic/condition_variable::wait%20Method.md)|スレッドをブロックします。|  
|[condition\_variable::wait\_for メソッド](../Topic/condition_variable::wait_for%20Method.md)|スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。|  
|[condition\_variable::wait\_until メソッド](../Topic/condition_variable::wait_until%20Method.md)|スレッドをブロックし、スレッドがブロック解除される最大の時刻を設定します。|  
  
## 必要条件  
 **ヘッダー:** condition\_variable  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<condition\_variable\>](../standard-library/condition-variable.md)