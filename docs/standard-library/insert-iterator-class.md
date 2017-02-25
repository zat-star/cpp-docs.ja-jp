---
title: "insert_iterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::insert_iterator"
  - "iterator/std::insert_iterator"
  - "std.insert_iterator"
  - "insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert_iterator クラス"
  - "insert_iterator クラス, 構文"
ms.assetid: d5d86405-872e-4e3b-9e68-c69a2b7e8221
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# insert_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

出力反復子の要件を満たす反復子アダプターについて説明します。  シーケンスに要素を上書きではなく、挿入し、C\+\+ のシーケンスと連想コンテナーの反復子が提供する上書きセマンティクスとは異なるセマンティクスを提供します。  `insert_iterator` クラスは、適合させるコンテナーの型でテンプレート化されます。  
  
## 構文  
  
```  
template <class Container> class insert_iterator;  
```  
  
#### パラメーター  
 `Container`  
 要素が `insert_iterator` によって挿入されるコンテナーの型。  
  
## 解説  
 **Container** 型のコンテナーは、可変サイズのコンテナーの要件を満たし、2 つの引数を取る insert メンバー関数を備えている必要があります。このメンバー関数のパラメーターは **Container::iterator** 型と **Container::value\_type** 型で、**Container::iterator** 型を返します。  標準テンプレート ライブラリ シーケンスおよび並べ替えられた連想コンテナーはこれらの要件を満たしており、`insert_iterator` で使用するために適合させることができます。  連想コンテナーでは、位置の引数はヒントとして扱われ、ヒントの品質に応じてパフォーマンスを向上させる場合も、低下させる場合もあります。  `insert_iterator` は、常に、コンテナーで初期化されている必要があります。  
  
### コンストラクター  
  
|||  
|-|-|  
|[insert\_iterator](../Topic/insert_iterator::insert_iterator.md)|コンテナーの指定された位置に要素を挿入する `insert_iterator` を構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[container\_type](../Topic/insert_iterator::container_type.md)|一般的な挿入の対象となるコンテナーを表す型。|  
|[参照](../Topic/insert_iterator::reference.md)|関連するコンテナーによって制御されるシーケンスの要素への参照を提供する型。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\*](../Topic/insert_iterator::operator*.md)|一般的な挿入のための出力反復子式 \*`i` \= `x` を実装するために使用される逆参照演算子。|  
|[operator\+\+](../Topic/insert_iterator::operator++.md)|値を格納できる次の位置に `insert_iterator` をインクリメントします。|  
|[operator\=](../Topic/insert_iterator::operator=.md)|一般的な挿入のための出力反復子式 \*`i` \= `x` を実装するために使用される代入演算子。|  
  
## 必要条件  
 **ヘッダー:** \<iterator\>  
  
 **名前空間:** std  
  
## 参照  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)