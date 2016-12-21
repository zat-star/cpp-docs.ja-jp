---
title: "forward_iterator_tag 構造体 | Microsoft Docs"
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
  - "std.forward_iterator_tag"
  - "forward_iterator_tag"
  - "std::forward_iterator_tag"
  - "xutility/std::forward_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_iterator_tag クラス"
  - "forward_iterator_tag 構造体"
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# forward_iterator_tag 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

前方反復子を表す **iterator\_category** 関数に戻り値の型を指定するクラス。  
  
## 構文  
  
```  
  
   struct forward_iterator_tag  
: public input_iterator_tag {};  
```  
  
## 解説  
 カテゴリのタグ クラスは、アルゴリズムの選択に対するコンパイル タグとして使用されます。  このテンプレート関数は、コンパイル時に最も効率的なアルゴリズムを使用できるように反復子の引数の特定のカテゴリは何かを確認する必要があります。  型 `Iterator`の反復子は、`iterator_traits`\<`Iterator`\>**::iterator\_category** は、反復子の動作を説明する特定のカテゴリのタグになるように定義する必要があります。  
  
 型は **反復子**\<**Iter**\>**::iterator\_category** と **Iter** が前方反復子として使用できるオブジェクトを表すと同じです。  
  
## 使用例  
 **iterator\_tag**s.を使用する方法の例については、" [iterator\_traits](../standard-library/iterator-traits-struct.md) または [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<反復子\>  
  
 **名前空間:** std  
  
## 参照  
 [input\_iterator\_tag 構造体](../standard-library/input-iterator-tag-struct.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)