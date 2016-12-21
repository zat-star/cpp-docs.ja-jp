---
title: "recursive_mutex クラス | Microsoft Docs"
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
  - "mutex/std::recursive_mutex"
dev_langs: 
  - "C++"
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# recursive_mutex クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*mutex 型*を表します。  [ミューテックス](../standard-library/mutex-class-stl.md)とは対照的に、既にロックされているオブジェクトのメソッドのロックの呼び出しの動作が正しく定義されています。  
  
## 構文  
  
```  
class recursive_mutex;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[recursive\_mutex::recursive\_mutex コンストラクター](../Topic/recursive_mutex::recursive_mutex%20Constructor.md)|`recursive_mutex` オブジェクトを構築します。|  
|[recursive\_mutex::~recursive\_mutex デストラクター](../Topic/recursive_mutex::~recursive_mutex%20Destructor.md)|`recursive_mutex` オブジェクトで使用されているリソースを解放します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[recursive\_mutex::lock メソッド](../Topic/recursive_mutex::lock%20Method.md)|スレッドがミューテックスの所有権を取得するまで呼び出し元スレッドをブロックします。|  
|[recursive\_mutex::try\_lock メソッド](../Topic/recursive_mutex::try_lock%20Method.md)|ブロックせずにミューテックスの所有権を取得しようとします。|  
|[recursive\_mutex::unlock メソッド](../Topic/recursive_mutex::unlock%20Method.md)|ミューテックスの所有権を解放します。|  
  
## 必要条件  
 **ヘッダー:** mutex  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)