---
title: "&lt;set&gt; | Microsoft Docs"
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
  - "std.<set>"
  - "std::<set>"
  - "<set>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set ヘッダー"
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;set&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナー テンプレート クラスの set と multiset、およびそのサポート用テンプレートを定義します。  
  
## 構文  
  
```  
  
#include <set>  
  
```  
  
## メンバー  
  
### 演算子  
  
|set のバージョン|multiset のバージョン|説明|  
|----------------|---------------------|--------|  
|[operator\!\= \(set\)](../Topic/operator!=%20\(set\).md)|[operator\!\= \(multiset\)](../Topic/operator!=%20\(multiset\).md)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトと等しくないかどうかをテストします。|  
|[operator\< \(set\)](../Topic/operator%3C%20\(set\).md)|[operator\< \(multiset\)](../Topic/operator%3C%20\(multiset\).md)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト未満かどうかをテストします。|  
|[operator\<\= \(set\)](../Topic/operator%3C=%20\(set\).md)|[operator\<\= \(multiset\)](../Topic/operator%3C=%20\(multiset\).md)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト以下かどうかをテストします。|  
|[operator\=\= \(set\)](../Topic/operator==%20\(set\).md)|[operator\=\= \(multiset\)](../Topic/operator==%20\(multiset\).md)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトと等しいかどうかをテストします。|  
|[operator\> \(set\)](../Topic/operator%3E%20\(set\).md)|[operator\> \(multiset\)](../Topic/operator%3E%20\(multiset\).md)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトより大きいかどうかをテストします。|  
|[operator\>\= \(set\)](../Topic/operator%3E=%20\(set\).md)|[operator\>\= \(multiset\)](../Topic/operator%3E=%20\(multiset\).md)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト以上かどうかをテストします。|  
  
### 特殊テンプレート関数  
  
|set のバージョン|multiset のバージョン|説明|  
|----------------|---------------------|--------|  
|[swap \(set\)](../Topic/swap%20\(set\).md)|[swap \(multiset\)](../Topic/swap%20\(multiset\).md)|2 つの set または multiset の要素を交換します。|  
  
### クラス  
  
|||  
|-|-|  
|[set クラス](../standard-library/set-class.md)|コレクションのデータを格納および取得するために使用されます。このコレクションに含まれる要素の値は一意です。この値はキー値として使用され、これに基づいてデータが自動的に順序付けられます。|  
|[multiset クラス](../Topic/multiset%20Class.md)|コレクションのデータを格納および取得するために使用されます。このコレクションに含まれる要素の値は一意とは限りません。この値はキー値として使用され、これに基づいてデータが自動的に順序付けられます。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)