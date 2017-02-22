---
title: "condition_variable_any クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "condition_variable/std::condition_variable_any"
dev_langs: 
  - "C++"
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# condition_variable_any クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`mutex` 型を持つイベントを待機するには、クラス `condition_variable_any` を使用します。  
  
## 構文  
  
```  
class condition_variable_any;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[condition\_variable\_any::condition\_variable\_any コンストラクター](../Topic/condition_variable_any::condition_variable_any%20Constructor.md)|`condition_variable_any` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[condition\_variable\_any::notify\_all メソッド](../Topic/condition_variable_any::notify_all%20Method.md)|`condition_variable_any` オブジェクトを待機しているすべてのスレッドのブロックを解除します。|  
|[condition\_variable\_any::notify\_one メソッド](../Topic/condition_variable_any::notify_one%20Method.md)|`condition_variable_any` オブジェクトを待機しているスレッドの 1 つのブロックを解除します。|  
|[condition\_variable\_any::wait メソッド](../Topic/condition_variable_any::wait%20Method.md)|スレッドをブロックします。|  
|[condition\_variable\_any::wait\_for メソッド](../Topic/condition_variable_any::wait_for%20Method.md)|スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。|  
|[condition\_variable\_any::wait\_until メソッド](../Topic/condition_variable_any::wait_until%20Method.md)|スレッドをブロックし、スレッドがブロック解除される最大の時刻を設定します。|  
  
## 必要条件  
 **ヘッダー:** condition\_variable  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<condition\_variable\>](../standard-library/condition-variable.md)