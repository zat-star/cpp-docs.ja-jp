---
title: "lock_guard クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::lock_guard"
dev_langs: 
  - "C++"
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# lock_guard クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

デストラクターが `mutex`をロック解除するオブジェクトを作成するにインスタンス化することができるテンプレートを表します。  
  
## 構文  
  
```  
template<class Mutex>  
class lock_guard;  
```  
  
## 解説  
 テンプレート引数 `Mutex` は *ミューテックスの型に名前を*付ける必要があります。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`lock_guard::mutex_type`|テンプレート引数 `Mutex`のシノニムです。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[lock\_guard::lock\_guard コンストラクター](../Topic/lock_guard::lock_guard%20Constructor.md)|`lock_guard` オブジェクトを構築します。|  
|[lock\_guard::~lock\_guard デストラクター](../Topic/lock_guard::~lock_guard%20Destructor.md)|`mutex` をロック解除をコンストラクターに渡された。|  
  
## 必要条件  
 **ヘッダー:** mutex  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)