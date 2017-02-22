---
title: "unordered_map クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::unordered_map"
  - "std.tr1.unordered_map"
  - "tr1.unordered_map"
  - "tr1::unordered_map"
  - "unordered_map"
  - "unordered_map/std::tr1::unordered_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_map クラス"
  - "unordered_map クラス [TR1]"
ms.assetid: 7cf7cfa1-16e7-461c-a9b2-3b8d8ec24e0d
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# unordered_map クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、`std::pair<const Key, Ty>` 型要素の可変長シーケンスを制御するオブジェクトを表します。  このシーケンスは、ハッシュ関数によって、"バケット" と呼ばれる一列に並んだサブシーケンスに分割され、弱い順序付けがなされます。  各バケット内では、比較関数によって要素間の大小関係が決定されます。  各要素は、並べ替えキーと値という、2 つのオブジェクトを持ちます。  このシーケンスは、すべてのバケットの長さがおおよそ等しければ、シーケンス内の要素数にかかわらず一定の演算回数 \(定数時間\) で、任意の要素を検索、挿入、削除できるような方法で表現されます。  最悪のケースは、すべての要素が 1 つのバケットに集められたときです。演算の回数は、シーケンス内の要素数に比例して増えることになります \(線形時間\)。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
## 構文  
  
```  
template<class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<std::pair<const Key, Ty> > >  
    class unordered_map;  
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
|[unordered\_map::allocator\_type](../Topic/unordered_map::allocator_type.md)|ストレージを管理するためのアロケーターの型です。|  
|[unordered\_map::const\_iterator](../Topic/unordered_map::const_iterator.md)|被制御シーケンスの定数反復子の型です。|  
|[unordered\_map::const\_local\_iterator](../Topic/unordered_map::const_local_iterator.md)|被制御シーケンスの定数バケット反復子の型です。|  
|[unordered\_map::const\_pointer](../Topic/unordered_map::const_pointer.md)|要素への定数ポインターの型です。|  
|[unordered\_map::const\_reference](../Topic/unordered_map::const_reference.md)|要素への定数参照の型です。|  
|[unordered\_map::difference\_type](../Topic/unordered_map::difference_type.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[unordered\_map::hasher](../Topic/unordered_map::hasher.md)|ハッシュ関数の型です。|  
|[unordered\_map::iterator](../Topic/unordered_map::iterator.md)|被制御シーケンスの反復子の型です。|  
|[unordered\_map::key\_equal](../Topic/unordered_map::key_equal.md)|比較関数の型です。|  
|[unordered\_map::key\_type](../Topic/unordered_map::key_type.md)|順序付けキーの型です。|  
|[unordered\_map::local\_iterator](../Topic/unordered_map::local_iterator.md)|被制御シーケンスのバケット反復子の型です。|  
|[unordered\_map::mapped\_type](../Topic/unordered_map::mapped_type.md)|各キーに関連付けられた、マップされた値の型です。|  
|[unordered\_map::pointer](../Topic/unordered_map::pointer.md)|要素へのポインターの型です。|  
|[unordered\_map::reference](../Topic/unordered_map::reference.md)|要素への参照の型です。|  
|[unordered\_map::size\_type](../Topic/unordered_map::size_type.md)|2 つの要素間の距離を表す、符号なしの型です。|  
|[unordered\_map::value\_type](../Topic/unordered_map::value_type.md)|要素の型。|  
  
|||  
|-|-|  
|メンバー関数|説明|  
|[unordered\_map::at](../Topic/unordered_map::at.md)|指定したキーを持つ要素を検索します。|  
|[unordered\_map::begin](../Topic/unordered_map::begin.md)|被制御シーケンスの先頭を指定します。|  
|[unordered\_map::bucket](../Topic/unordered_map::bucket.md)|キー値のバケット番号を取得します。|  
|[unordered\_map::bucket\_count](../Topic/unordered_map::bucket_count.md)|バケット数を取得します。|  
|[unordered\_map::bucket\_size](../Topic/unordered_map::bucket_size.md)|バケットのサイズを取得します。|  
|[unordered\_map::cbegin](../Topic/unordered_map::cbegin.md)|被制御シーケンスの先頭を指定します。|  
|[unordered\_map::cend](../Topic/unordered_map::cend.md)|被制御シーケンスの末尾を指定します。|  
|[unordered\_map::clear](../Topic/unordered_map::clear.md)|すべての要素を削除します。|  
|[unordered\_map::count](../Topic/unordered_map::count.md)|指定したキーに一致する要素の数を検索します。|  
|[unordered\_map::emplace](../Topic/unordered_map::emplace.md)|構築された要素を適切な場所に追加します。|  
|[unordered\_map::emplace\_hint](../Topic/unordered_map::emplace_hint.md)|構築された要素を適切な場所にヒントと一緒に追加します。|  
|[unordered\_map::empty](../Topic/unordered_map::empty.md)|要素が存在しないかどうかをテストします。|  
|[unordered\_map::end](../Topic/unordered_map::end.md)|被制御シーケンスの末尾を指定します。|  
|[unordered\_map::equal\_range](../Topic/unordered_map::equal_range.md)|指定したキーに一致する範囲を検索します。|  
|[unordered\_map::erase](../Topic/unordered_map::erase.md)|指定した位置にある要素を削除します。|  
|[unordered\_map::find](../Topic/unordered_map::find.md)|指定したキーに一致する要素を検索します。|  
|[unordered\_map::get\_allocator](../Topic/unordered_map::get_allocator.md)|格納されているアロケーター オブジェクトを取得します。|  
|[unordered\_map::hash\_function](../Topic/unordered_map::hash_function.md)|格納されているハッシュ関数オブジェクトを取得します。|  
|[unordered\_map::insert](../Topic/unordered_map::insert.md)|要素を追加します。|  
|[unordered\_map::key\_eq](../Topic/unordered_map::key_eq.md)|格納されている比較関数オブジェクトを取得します。|  
|[unordered\_map::load\_factor](../Topic/unordered_map::load_factor.md)|バケットごとの平均要素数をカウントします。|  
|[unordered\_map::max\_bucket\_count](../Topic/unordered_map::max_bucket_count.md)|最大バケット数を取得します。|  
|[unordered\_map::max\_load\_factor](../Topic/unordered_map::max_load_factor.md)|バケットあたりの最大要素数を取得または設定します。|  
|[unordered\_map::max\_size](../Topic/unordered_map::max_size.md)|被制御シーケンスの最大サイズを取得します。|  
|[unordered\_map::rehash](../Topic/unordered_map::rehash.md)|ハッシュ テーブルをリビルドします。|  
|[unordered\_map::size](../Topic/unordered_map::size.md)|要素の数をカウントします。|  
|[unordered\_map::swap](../Topic/unordered_map::swap.md)|2 つのコンテナーのコンテンツを交換します。|  
|[unordered\_map::unordered\_map](../Topic/unordered_map::unordered_map.md)|コンテナー オブジェクトを構築します。|  
  
|||  
|-|-|  
|\[演算子\]|説明|  
|[unordered\_map::operator](../Topic/unordered_map::operator.md)|指定したキーを持つ要素を検索または挿入します。|  
|[unordered\_map::operator\=](../Topic/unordered_map::operator=.md)|ハッシュ テーブルをコピーします。|  
  
## 解説  
 このオブジェクトは、このオブジェクトが制御するシーケンスを、格納されている 2 つのオブジェクト \([unordered\_map::key\_equal](../Topic/unordered_map::key_equal.md) 型の比較関数オブジェクトと、[unordered\_map::hasher](../Topic/unordered_map::hasher.md) 型のハッシュ関数オブジェクト\) を呼び出すことによって並べ替えます。  格納されている 1 つ目のオブジェクトには、メンバー関数 [unordered\_map::key\_eq](../Topic/unordered_map::key_eq.md)`()` を呼び出すことによってアクセスします。格納されている 2 つ目のオブジェクトには、メンバー関数 [unordered\_map::hash\_function](../Topic/unordered_map::hash_function.md)`()` を呼び出すことによってアクセスします。  具体的には、`Key` 型のすべての値 `X` と `Y` について、`key_eq()(X, Y)` が呼び出され、2 つの引数値の大小関係が等しい場合は true が返されます。`hash_function()(keyval)` の呼び出しからは、`size_t` 型の値の分布が生成されます。  [unordered\_multimap クラス](../standard-library/unordered-multimap-class.md) テンプレート クラスとは異なり、`unordered_map` テンプレート クラスのオブジェクトでは、被制御シーケンスの任意の 2 つの要素間で `key_eq()(X, Y)` が常に false になることが保証されます。キーの重複は許されません。  
  
 このオブジェクトには、さらに、適切とされるバケットあたりの最大平均要素数を指定する最大テーブル占有率が格納されます。  要素を挿入することによって [unordered\_map::load\_factor](../Topic/unordered_map::load_factor.md)`()` が最大テーブル占有率を超えるような場合、コンテナーは、バケット数を増やし、必要に応じて、ハッシュ テーブルをリビルドします。  
  
 被制御シーケンスにおける要素の実際の順序は、ハッシュ関数、比較関数、挿入の順序、最大テーブル占有率、現在のバケット数などによって異なります。  通常、被制御シーケンス内の要素の順序を予測することはできません。  ただし、被制御シーケンス内で同じ大小関係を持った一連の要素は必ず隣接して存在します。  
  
 被制御シーケンスに対するストレージの割り当ておよび解放は、格納されている [unordered\_map::allocator\_type](../Topic/unordered_map::allocator_type.md) 型のアロケーター オブジェクトを介して行われます。  このアロケーター オブジェクトは、`allocator` テンプレート クラスのオブジェクトと同じ外部インターフェイスを持っている必要があります。  コンテナー オブジェクトを代入しても、格納されているアロケーター オブジェクトはコピーされない点に注意してください。  
  
## 必要条件  
 **ヘッダー:** \<unordered\_map\>  
  
 **名前空間:** std  
  
## 参照  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [コンテナー](../Topic/Containers%20\(Modern%20C++\).md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)