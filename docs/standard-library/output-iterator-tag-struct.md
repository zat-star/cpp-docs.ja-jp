---
title: "output_iterator_tag 構造体 | Microsoft Docs"
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
  - "std::output_iterator_tag"
  - "output_iterator_tag"
  - "xutility/std::output_iterator_tag"
  - "std.output_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "output_iterator_tag クラス"
  - "output_iterator_tag 構造体"
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# output_iterator_tag 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

出力反復子を表す **iterator\_category** 関数の戻り値の型を提供するクラス。  
  
## 構文  
  
```  
  
struct output_iterator_tag {};  
  
```  
  
## 解説  
 カテゴリ タグ クラスは、アルゴリズムの選択範囲のタグのコンパイルに使用されます。 テンプレート関数は、コンパイル時に、最も効率的なアルゴリズムを使用できるように反復子引数の特定のカテゴリを検索する必要があります。 型のすべての反復子の `Iterator`, 、`iterator_traits`\<`Iterator`\>**:: iterator\_category** 反復子の動作を説明する具体的なカテゴリ タグを定義する必要があります。  
  
 型が同じ **反復子**\<**Iter**\>**:: iterator\_category** と **Iter** 出力反復子として使用できるオブジェクトを表します。  
  
 このタグは、パラメーター化されていない、 `value_type` または `difference_type` 、反復子のと同様に、その他の反復子タグ出力反復子がいずれかがあるないため、 `value_type` または `difference_type`です。  
  
## 使用例  
 参照してください [iterator\_traits](../standard-library/iterator-traits-struct.md) または [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) を使用する方法の例については **iterator\_tag**秒です。  
  
## 必要条件  
 **ヘッダー:**\<iterator\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)