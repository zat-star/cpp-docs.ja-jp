---
title: "unordered_multimap クラス | Microsoft Docs"
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
  - "unordered_map/std::tr1::unordered_multimap"
  - "tr1.unordered_multimap"
  - "unordered_multimap"
  - "std.tr1.unordered_multimap"
  - "tr1::unordered_multimap"
  - "std::tr1::unordered_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_multimap クラス"
  - "unordered_multimap クラス [TR1]"
ms.assetid: 4baead6c-5870-4b85-940f-a47d6b891c27
caps.latest.revision: 28
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unordered_multimap クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、`std::pair<const Key, Ty>` 型要素の可変長シーケンスを制御するオブジェクトを表します。  このシーケンスは、ハッシュ関数によって、"バケット" と呼ばれる一列に並んだサブシーケンスに分割され、弱い順序付けがなされます。  各バケット内では、比較関数によって要素間の大小関係が決定されます。  各要素は、並べ替えキーと値という、2 つのオブジェクトを持ちます。  このシーケンスは、すべてのバケットの長さがおおよそ等しければ、シーケンス内の要素数にかかわらず一定の演算回数 \(定数時間\) で、任意の要素を検索、挿入、削除できるような方法で表現されます。  最悪のケースは、すべての要素が 1 つのバケットに集められたときです。演算の回数は、シーケンス内の要素数に比例して増えることになります \(線形時間\)。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
## 構文  
  
```  
template<class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_multimap;  
```  
  
#### パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|`Key`|キーの型。|  
|`Ty`|マップされた型。|  
|`Hash`|ハッシュ関数のオブジェクト型。|  
|`Pred`|等価比較関数のオブジェクト型。|  
|`Alloc`|アロケーター クラス。|  
  
## メンバー  
  
|||  
|-|-|  
|型定義|説明|  
|[unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md)|ストレージを管理するためのアロケーターの型です。|  
|[unordered\_multimap::const\_iterator](../Topic/unordered_multimap::const_iterator.md)|被制御シーケンスの定数反復子の型です。|  
|[unordered\_multimap::const\_local\_iterator](../Topic/unordered_multimap::const_local_iterator.md)|被制御シーケンスの定数バケット反復子の型です。|  
|[unordered\_multimap::const\_pointer](../Topic/unordered_multimap::const_pointer.md)|要素への定数ポインターの型です。|  
|[unordered\_multimap::const\_reference](../Topic/unordered_multimap::const_reference.md)|要素への定数参照の型です。|  
|[unordered\_multimap::difference\_type](../Topic/unordered_multimap::difference_type.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md)|ハッシュ関数の型です。|  
|[unordered\_multimap::iterator](../Topic/unordered_multimap::iterator.md)|被制御シーケンスの反復子の型です。|  
|[unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md)|比較関数の型です。|  
|[unordered\_multimap::key\_type](../Topic/unordered_multimap::key_type.md)|順序付けキーの型です。|  
|[unordered\_multimap::local\_iterator](../Topic/unordered_multimap::local_iterator.md)|被制御シーケンスのバケット反復子の型です。|  
|[unordered\_multimap::mapped\_type](../Topic/unordered_multimap::mapped_type.md)|各キーに関連付けられた、マップされた値の型です。|  
|[unordered\_multimap::pointer](../Topic/unordered_multimap::pointer.md)|要素へのポインターの型です。|  
|[unordered\_multimap::reference](../Topic/unordered_multimap::reference.md)|要素への参照の型です。|  
|[unordered\_multimap::size\_type](../Topic/unordered_multimap::size_type.md)|2 つの要素間の距離を表す、符号なしの型です。|  
|[unordered\_multimap::value\_type](../Topic/unordered_multimap::value_type.md)|要素の型。|  
  
|||  
|-|-|  
|メンバー関数|説明|  
|[unordered\_multimap::begin](../Topic/unordered_multimap::begin.md)|被制御シーケンスの先頭を指定します。|  
|[unordered\_multimap::bucket](../Topic/unordered_multimap::bucket.md)|キー値のバケット番号を取得します。|  
|[unordered\_multimap::bucket\_count](../Topic/unordered_multimap::bucket_count.md)|バケット数を取得します。|  
|[unordered\_multimap::bucket\_size](../Topic/unordered_multimap::bucket_size.md)|バケットのサイズを取得します。|  
|[unordered\_multimap::cbegin](../Topic/unordered_multimap::cbegin.md)|被制御シーケンスの先頭を指定します。|  
|[unordered\_multimap::cend](../Topic/unordered_multimap::cend.md)|被制御シーケンスの末尾を指定します。|  
|[unordered\_multimap::clear](../Topic/unordered_multimap::clear.md)|すべての要素を削除します。|  
|[unordered\_multimap::count](../Topic/unordered_multimap::count.md)|指定したキーに一致する要素の数を検索します。|  
|[unordered\_multimap::emplace](../Topic/unordered_multimap::emplace.md)|構築された要素を適切な場所に追加します。|  
|[unordered\_multimap::emplace\_hint](../Topic/unordered_multimap::emplace_hint.md)|構築された要素を適切な場所にヒントと一緒に追加します。|  
|[unordered\_multimap::empty](../Topic/unordered_multimap::empty.md)|要素が存在しないかどうかをテストします。|  
|[unordered\_multimap::end](../Topic/unordered_multimap::end.md)|被制御シーケンスの末尾を指定します。|  
|[unordered\_multimap::equal\_range](../Topic/unordered_multimap::equal_range.md)|指定したキーに一致する範囲を検索します。|  
|[unordered\_multimap::erase](../Topic/unordered_multimap::erase.md)|指定した位置にある要素を削除します。|  
|[unordered\_multimap::find](../Topic/unordered_multimap::find.md)|指定したキーに一致する要素を検索します。|  
|[unordered\_multimap::get\_allocator](../Topic/unordered_multimap::get_allocator.md)|格納されているアロケーター オブジェクトを取得します。|  
|[unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)|格納されているハッシュ関数オブジェクトを取得します。|  
|[unordered\_multimap::insert](../Topic/unordered_multimap::insert.md)|要素を追加します。|  
|[unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md)|格納されている比較関数オブジェクトを取得します。|  
|[unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)|バケットごとの平均要素数をカウントします。|  
|[unordered\_multimap::max\_bucket\_count](../Topic/unordered_multimap::max_bucket_count.md)|最大バケット数を取得します。|  
|[unordered\_multimap::max\_load\_factor](../Topic/unordered_multimap::max_load_factor.md)|バケットあたりの最大要素数を取得または設定します。|  
|[unordered\_multimap::max\_size](../Topic/unordered_multimap::max_size.md)|被制御シーケンスの最大サイズを取得します。|  
|[unordered\_multimap::rehash](../Topic/unordered_multimap::rehash.md)|ハッシュ テーブルをリビルドします。|  
|[unordered\_multimap::size](../Topic/unordered_multimap::size.md)|要素の数をカウントします。|  
|[unordered\_multimap::swap](../Topic/unordered_multimap::swap.md)|2 つのコンテナーのコンテンツを交換します。|  
|[unordered\_multimap::unordered\_multimap](../Topic/unordered_multimap::unordered_multimap.md)|コンテナー オブジェクトを構築します。|  
  
|||  
|-|-|  
|演算子|説明|  
|[unordered\_multimap::operator\=](../Topic/unordered_multimap::operator=.md)|ハッシュ テーブルをコピーします。|  
  
## 解説  
 このオブジェクトは、このオブジェクトが制御するシーケンスを、格納されている 2 つのオブジェクト \([unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md) 型の比較関数オブジェクトと、[unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md) 型のハッシュ関数オブジェクト\) を呼び出すことによって並べ替えます。  格納されている 1 つ目のオブジェクトには、メンバー関数 [unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md)`()` を呼び出すことによってアクセスします。格納されている 2 つ目のオブジェクトには、メンバー関数 [unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)`()` を呼び出すことによってアクセスします。  具体的には、`Key` 型のすべての値 `X` と `Y` について、`key_eq()(X, Y)` が呼び出され、2 つの引数値の大小関係が等しい場合は true が返されます。`hash_function()(keyval)` の呼び出しからは、`size_t` 型の値の分布が生成されます。  [unordered\_map クラス](../standard-library/unordered-map-class.md) テンプレート クラスとは異なり、`unordered_multimap` テンプレート クラスのオブジェクトでは、被制御シーケンスの任意の 2 つの要素間で `key_eq()(X, Y)` が常に false になるとは限りません。つまり、キーの重複が許されることになります。  
  
 このオブジェクトには、さらに、適切とされるバケットあたりの最大平均要素数を指定する最大テーブル占有率が格納されます。  要素を挿入することによって [unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)`()` が最大テーブル占有率を超えるような場合、コンテナーは、バケット数を増やし、必要に応じて、ハッシュ テーブルをリビルドします。  
  
 被制御シーケンスにおける要素の実際の順序は、ハッシュ関数、比較関数、挿入の順序、最大テーブル占有率、現在のバケット数などによって異なります。  通常、被制御シーケンス内の要素の順序を予測することはできません。  ただし、被制御シーケンス内で同じ大小関係を持った一連の要素は必ず隣接して存在します。  
  
 被制御シーケンスに対するストレージの割り当ておよび解放は、格納されている [unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md) 型のアロケーター オブジェクトを介して行われます。  このアロケーター オブジェクトは、`allocator` テンプレート クラスのオブジェクトと同じ外部インターフェイスを持っている必要があります。  コンテナー オブジェクトを代入しても、格納されているアロケーター オブジェクトはコピーされない点に注意してください。  
  
## 必要条件  
 **ヘッダー:** \<unordered\_map\>  
  
 **名前空間:** std  
  
## 参照  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [コンテナー](../Topic/Containers%20\(Modern%20C++\).md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)