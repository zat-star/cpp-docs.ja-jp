---
title: "&lt;utility&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<utility>"
  - "utility/std::<utility>"
  - "std.<utility>"
  - "std::<utility>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "utility ヘッダー"
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

標準テンプレート ライブラリ \(STL\) の型、関数、および演算子を定義し、オブジェクトのペアを作成し管理するのに役立てます。これらは 2 つのオブジェクトをあたかも 1 つのように扱う必要がある場合に役立ちます。  
  
## 構文  
  
```  
  
#include <utility>  
  
```  
  
## 解説  
 ペアは、標準 C\+\+ ライブラリで広く使用されます。  これはさまざまな関数の引数と戻り値として、また [map クラス](../Topic/map%20Class.md) と [multimap クラス](../standard-library/multimap-class.md) などのコンテナーの要素型として必要です。  \<utility\> ヘッダーは、キー\/値ペア型の要素の管理を補助するために、\<map\> により自動で追加されます。  
  
### クラス  
  
|||  
|-|-|  
|[tuple\_element](../standard-library/tuple-element-class-utility.md)|`pair` 要素の型をラップするクラスです。|  
|[tuple\_size](../standard-library/tuple-size-class-utility.md)|`pair` 要素の数をラップするクラスです。|  
  
### Functions  
  
|||  
|-|-|  
|[forward](../Topic/forward.md)|引数の参照型 \(`lvalue` または `rvalue` のどちらか\) が完全転送によって隠されないよう保ちます。|  
|[取得](../Topic/get%20Function%20%3Cutility%3E.md)|`pair` オブジェクトから要素を取得する関数です。|  
|[make\_pair](../Topic/make_pair.md)|`pair` 型のオブジェクトを作成するために使用されるテンプレート ヘルパー関数。コンポーネントの型は、パラメーターとして渡されるデータ型に基づいています。|  
|[移動](../Topic/move.md)|`rvalue` 参照として引数で渡されたものを返します。|  
|[swap](../Topic/swap%20\(%3Cutility%3E\).md)|2 つの `pair` オブジェクトの要素を交換します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Cutility%3E\).md)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトと等しくないかどうかを調べます。|  
|[operator\=\=](../Topic/operator==%20\(%3Cutility%3E\).md)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトと等しいかどうかを調べます。|  
|[\< 演算子](../Topic/operator%3C%20\(%3Cutility%3E\).md)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトより小さいかどうかを調べます。|  
|[\<\= 演算子](../Topic/operator%3C=%20\(%3Cutility%3E\).md)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクト以下かどうかを調べます。|  
|[\> 演算子](../Topic/operator%3E%20\(%3Cutility%3E\).md)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトより大きいかどうかを調べます。|  
|[\>\= 演算子](../Topic/operator%3E=%20\(%3Cutility%3E\).md)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクト以上かどうかを調べます。|  
  
### 構造体  
  
|||  
|-|-|  
|[ID](../Topic/identity%20Structure.md)||  
|[pair](../standard-library/pair-structure.md)|2 つのオブジェクトを 1 つのオブジェクトとして処理する機能を提供する型。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)