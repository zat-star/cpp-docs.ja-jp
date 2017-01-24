---
title: "reverse_iterator クラス | Microsoft Docs"
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
  - "reverse_iterator"
  - "std::reverse_iterator"
  - "std.reverse_iterator"
  - "xutility/std::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator クラス"
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
caps.latest.revision: 21
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# reverse_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、逆方向でのみランダム アクセス反復子または双方向反復子のように動作する反転反復子オブジェクトを表す反復子アダプターです。  これは範囲の後方走査を有効にします。  
  
## 構文  
  
```  
template <class RandomIterator>  
class reverse_iterator  
```  
  
#### パラメーター  
 RandomIterator  
 逆方向に動作するように適合させる反復子を表す型。  
  
## 解説  
 既存の標準テンプレート ライブラリのコンテナーは、`reverse_iterator` 型および `const_reverse_iterator` 型も定義し、反転反復子を返すメンバー関数 `rbegin` および `rend` を備えています。  これらの反復子には、上書きセマンティクスがあります。  `reverse_iterator` アダプターは、この機能を補完して挿入セマンティクスを提供し、ストリームで使用できるようにします。  
  
 双方向反復子を必要とする `reverse_iterator` で、ランダム アクセス反復子でのみ使用できるメンバー関数 `operator+=`、`operator+`、`operator-=`、`operator-`、または `operator[]` を呼び出すことはできません。  
  
 反復子の範囲が \[`_First`, \_Last\) である場合、左側の角かっこは \_*First* を包むことを指定し、右側のかっこは \_*Left* に至るまでの要素は含むが、\_*Left* 自体は除外することを指定します。  同じ要素が反転シーケンス \[**rev** – `_First`, **rev** – \_*Left*\) に含まれます。\_*Left* がシーケンス内で末尾の 1 つ次の要素である場合、反転シーケンス内の最初の要素 **rev** – \_*First* は \*\(\_*Left* – 1 \) を指します。  すべての反転反復子を基になる反復子に関連付ける識別子は、次のとおりです。  
  
 &\*\(**reverse\_iterator** \( *i* \) \) \=\= &\*\( *i* – 1 \).  
  
 実際には、反転シーケンスで reverse\_iterator は、元のシーケンスで反復子が参照する要素の 1 つ次の \(右側にある\) 要素を参照することを意味します。  したがって、反復子がシーケンス \(2、4、6、8\) で要素 6 を指定する場合、`reverse_iterator` は反転シーケンス \(8、6、4、2\) の 4 要素を指定します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[reverse\_iterator](../Topic/reverse_iterator::reverse_iterator.md)|基になる反復子の既定の `reverse_iterator` または `reverse_iterator` を構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[difference\_type](../Topic/reverse_iterator::difference_type.md)|同じコンテナー内の要素を参照する 2 つの `reverse_iterator` の違いを提供する型。|  
|[iterator\_type](../Topic/reverse_iterator::iterator_type.md)|`reverse_iterator` に基になる反復子を提供する型。|  
|[pointer](../Topic/reverse_iterator::pointer.md)|`reverse_iterator` によってアドレス指定される要素へのポインターを提供する型。|  
|[参照](../Topic/reverse_iterator::reference.md)|`reverse_iterator` によってアドレス指定される要素への参照を提供する型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[base](../Topic/reverse_iterator::base.md)|その `reverse_iterator` から基になる反復子を復元します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\*](../Topic/reverse_iterator::operator*.md)|`reverse_iterator` がアドレス指定する要素を返します。|  
|[operator\+](../Topic/reverse_iterator::operator+.md)|反復子にオフセットを追加し、新しいオフセット位置に挿入された要素をアドレス指定する新しい `reverse_iterator` アドレスを返します。|  
|[operator\+\+](../Topic/reverse_iterator::operator++.md)|`reverse_iterator` を次の要素にインクリメントします。|  
|[operator\+\=](../Topic/reverse_iterator::operator+=.md)|指定したオフセットを `reverse_iterator` から追加します。|  
|[operator\-](../Topic/reverse_iterator::operator-.md)|`reverse_iterator` からオフセットを減算し、オフセット位置にある要素を指定する `reverse_iterator` を返します。|  
|[operator\-\-](../Topic/reverse_iterator::operator--.md)|`reverse_iterator` を直前の要素にデクリメントします。|  
|[operator\-\=](../Topic/reverse_iterator::operator-=.md)|指定されたオフセットを `reverse_iterator` から減算します。|  
|[operator\-\>](../Topic/reverse_iterator::operator-%3E.md)|`reverse_iterator` によってアドレス指定される要素へのポインターを返します。|  
|[operator&#91;&#93;](../Topic/reverse_iterator::operator.md)|`reverse_iterator` によってアドレス指定される要素からの要素のオフセットへの参照を返します。|  
  
## 必要条件  
 **ヘッダー:** \<iterator\>  
  
 **名前空間:** std  
  
## 参照  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)