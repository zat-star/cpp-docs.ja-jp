---
title: "&lt;typeindex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<typeindex>"
dev_langs: 
  - "C++"
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# &lt;typeindex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスを定義し、\<操作するために標準ヘッダーの typeindex\> が、クラス [type\_info](../cpp/type-info-class.md)オブジェクトの作成をサポートする。  
  
## 構文  
  
```cpp  
#include <typeindex>  
```  
  
## 解説  
 [hash 構造体](../standard-library/hash-structure.md) は `hash function` を定義するインデックス値の分布に型 [type\_index](../standard-library/type-index-class.md) の値を割り当てるときに適しています。  
  
 `type_index` クラスは、インデックスのサポートに `type_info` オブジェクトへのポインターをラップします。  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)