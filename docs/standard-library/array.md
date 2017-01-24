---
title: "&lt;array&gt; | Microsoft Docs"
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
  - "<array>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array ヘッダー [TR1]"
ms.assetid: 084147c1-e805-478e-8201-76846020f187
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;array&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナーのテンプレート クラス `array` と複数のサポート用テンプレートを定義します。  
  
## 構文  
  
```  
#include <array>  
```  
  
### クラス  
  
|||  
|-|-|  
|[array](../standard-library/array-class-stl.md)|要素の固定長シーケンスを格納します。|  
|[tuple\_element](../standard-library/tuple-element-class-array.md)|配列の要素の型をラップします。|  
|[tuple\_size](../standard-library/tuple-size-class-array.md)|配列要素のサイズをラップします。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20%3Carray%3E.md)|配列の大小関係 \(等しい\)|  
|[operator\!\=](../Topic/operator!=%20%3Carray%3E.md)|配列の大小関係 \(等しくない\) はありません。|  
|[operator\<](../Topic/operator%3C%20%3Carray%3E.md)|配列の大小関係 \(より小さい\)|  
|[operator\>\=](../Topic/operator%3E=%20%3Carray%3E.md)|配列の大小関係 \(以上\)|  
|[operator\>](../Topic/operator%3E%20%3Carray%3E.md)|配列の大小関係 \(|  
|[operator\<\=](../Topic/operator%3C=%20%3Carray%3E.md)|より小さいか等しい配列の比較|  
  
### 関数  
  
|||  
|-|-|  
|[get](../Topic/get%20Function%20%3Carray%3E.md)|指定した配列の要素を取得します。|  
|[swap](../Topic/swap%20Function%20%3Carray%3E.md)|別の配列の内容と 1 個の配列の内容を交換します。|  
  
## 参照  
 [\<tuple\>](../standard-library/tuple.md)   
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)