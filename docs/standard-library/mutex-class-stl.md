---
title: "mutex クラス (STL) | Microsoft Docs"
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
  - "mutex/std::mutex"
dev_langs: 
  - "C++"
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mutex クラス (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*mutex 型*を表します。  この型のオブジェクトを使用して、プログラム内で相互排他を適用できます。  
  
## 構文  
  
```  
class mutex;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[mutex::mutex コンストラクター \(STL\)](../Topic/mutex::mutex%20Constructor%20\(STL\).md)|`mutex` オブジェクトを構築します。|  
|[mutex::~mutex デストラクター \(STL\)](../Topic/mutex::~mutex%20Destructor%20\(STL\).md)|`mutex` オブジェクトで使用されたすべてのリソースを解放します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[mutex::lock メソッド \(STL\)](../Topic/mutex::lock%20Method%20\(STL\).md)|呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。|  
|[mutex::native\_handle メソッド \(STL\)](../Topic/mutex::native_handle%20Method%20\(STL\).md)|ミューテックス ハンドルを表す実装固有の型を返します。|  
|[mutex::try\_lock メソッド \(STL\)](../Topic/mutex::try_lock%20Method%20\(STL\).md)|ブロックせずに `mutex` の所有権を取得しようとします。|  
|[mutex::unlock メソッド \(STL\)](../Topic/mutex::unlock%20Method%20\(STL\).md)|`mutex` の所有権を解放します。|  
  
## 必要条件  
 **ヘッダー:** mutex  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)