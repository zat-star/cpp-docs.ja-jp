---
title: "array クラス (STL) | Microsoft Docs"
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
  - "array/std::tr1::array"
  - "std.tr1.array"
  - "array"
  - "std::tr1::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array クラス [TR1]"
ms.assetid: fdfd43a5-b2b5-4b9e-991f-93bf10fb4293
caps.latest.revision: 22
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# array クラス (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

長さ `N` の `Ty` 型の要素のシーケンスを制御するオブジェクトを記述します。  このシーケンスは、`array<Ty, N>` オブジェクト内に含まれる `Ty` の配列として格納されます。  
  
## 構文  
  
```  
template<class Ty, std::size_t N>  
    class array;  
```  
  
#### パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|`Ty`|要素の型。|  
|`N`|要素の数。|  
  
## メンバー  
  
|||  
|-|-|  
|型定義|説明|  
|[array::const\_iterator](../Topic/array::const_iterator.md)|被制御シーケンスの定数反復子の型です。|  
|[array::const\_pointer](../Topic/array::const_pointer.md)|要素への定数ポインターの型です。|  
|[array::const\_reference](../Topic/array::const_reference.md)|要素への定数参照の型です。|  
|[array::const\_reverse\_iterator](../Topic/array::const_reverse_iterator.md)|被制御シーケンスの定数反転反復子の型です。|  
|[array::difference\_type](../Topic/array::difference_type.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[array::iterator](../Topic/array::iterator.md)|被制御シーケンスの反復子の型です。|  
|[array::pointer](../Topic/array::pointer.md)|要素へのポインターの型です。|  
|[array::reference](../Topic/array::reference.md)|要素への参照の型です。|  
|[array::reverse\_iterator](../Topic/array::reverse_iterator.md)|被制御シーケンスの反転反復子の型です。|  
|[array::size\_type](../Topic/array::size_type.md)|2 つの要素間の距離を表す、符号なしの型です。|  
|[array::value\_type](../Topic/array::value_type.md)|要素の型。|  
  
|||  
|-|-|  
|メンバー関数|説明|  
|[array::array](../Topic/array::array.md)|配列オブジェクトを構築します。|  
|[array::assign](../Topic/array::assign.md)|すべての要素を置換します。|  
|[array::at](../Topic/array::at.md)|指定した位置にある要素にアクセスします。|  
|[array::back](../Topic/array::back.md)|最後の要素にアクセスします。|  
|[array::begin](../Topic/array::begin.md)|被制御シーケンスの先頭を指定します。|  
|[array::cbegin](../Topic/array::cbegin.md)|配列内の最初の要素を示すランダム アクセスの定数反復子を返します。|  
|[array::cend](../Topic/array::cend.md)|配列の末尾の次の位置を指し示すランダム アクセス定数反復子を返します。|  
|[array::crbegin](../Topic/array::crbegin.md)|反転された配列内の最初の要素への定数反復子を返します。|  
|[array::crend](../Topic/array::crend.md)|反転された配列内の末尾の要素への定数反復子を返します。|  
|[array::data](../Topic/array::data.md)|最初の要素のアドレスを取得します。|  
|[array::empty](../Topic/array::empty.md)|要素が存在するかどうかをテストします。|  
|[array::end](../Topic/array::end.md)|被制御シーケンスの末尾を指定します。|  
|[array::fill](../Topic/array::fill.md)|すべての要素を、指定された値に置き換えます。|  
|[array::front](../Topic/array::front.md)|最初の要素にアクセスします。|  
|[array::max\_size](../Topic/array::max_size.md)|要素の数をカウントします。|  
|[array::rbegin](../Topic/array::rbegin.md)|反転被制御シーケンスの先頭を指定します。|  
|[array::rend](../Topic/array::rend.md)|反転被制御シーケンスの末尾を指定します。|  
|[array::size](../Topic/array::size.md)|要素の数をカウントします。|  
|[array::swap](../Topic/array::swap.md)|2 つのコンテナーのコンテンツを交換します。|  
  
|||  
|-|-|  
|演算子|説明|  
|[array::operator\=](../Topic/array::operator=.md)|被制御シーケンスを置き換えます。|  
|[array::operator](../Topic/array::operator.md)|指定した位置にある要素にアクセスします。|  
  
## 解説  
 この型は、既定のコンストラクター `array()` と既定代入演算子 `operator=` を持ち、`aggregate` の要件を満たします。  そのため、`array<Ty, N>` 型のオブジェクトは、集計初期化子を使用して初期化できます。  次に例を示します。  
  
```  
array<int, 4> ai = { 1, 2, 3 };  
```  
  
 このコードは、4 つの整数値を保持するオブジェクト `ai` を作成し、最初の 3 つの要素はそれぞれ値 1、2、3 に初期化し、4 番目の要素は 0 に初期化します。  
  
## 必要条件  
 **ヘッダー:** \<array\>  
  
 **名前空間:** std  
  
## 参照  
 [\<array\>](../standard-library/array.md)