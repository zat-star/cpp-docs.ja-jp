---
title: "vector&lt;bool&gt;::reference クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vector<bool>::reference"
  - "std::vector<bool>::reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector<bool> 参照クラス"
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# vector&lt;bool&gt;::reference クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`vector<bool>::reference` クラスは `bool&` をシミュレートするために [vector\<bool\> クラス](../Topic/vector%3Cbool%3E%20Class.md)によって提供されるプロキシ クラスです。  
  
## 解説  
 C\+\+ では、ネイティブにビットを直接参照しないため、シミュレートされた参照が必要です。  `vector<bool>` は、要素ごとに 1 ビットだけ使用します。このビットは、このプロキシ クラスを使用して参照できます。  ただし、参照のシミュレーションは、特定の代入が有効でないため、完全ではありません。  たとえば、`vector<bool>::reference` オブジェクトのアドレスを受け取ることができないため、[vector\<bool\>::operator &#91;&#93;](../Topic/vector%3Cbool%3E::operator.md) を使用する次のコードは正しくありません。  
  
```cpp  
    vector<bool> vb;  
...  
    bool* pb = &vb[1]; // conversion error - do not use  
    bool& refb = vb[1];   // conversion error - do not use  
  
```  
  
### メンバー関数  
  
|||  
|-|-|  
|[flip](../standard-library/vector-bool-reference-flip.md)|vector 要素のブール値を反転します。|  
|[operator bool](../Topic/vector%3Cbool%3E::reference::operator%20bool.md)|`vector<bool>::reference` から `bool` への暗黙の変換を提供します。|  
|[operator\=](../standard-library/vector-bool-reference-operator-assign.md)|ブール値をビットに割り当てます。または参照先の要素が保持している値をビットに割り当てます。|  
  
## 要件  
 **ヘッダー:** \<vector\>  
  
 **名前空間:** std  
  
## 参照  
 [\<vector\>](../standard-library/vector.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)