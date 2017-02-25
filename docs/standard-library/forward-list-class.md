---
title: "forward_list クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::forward_list"
  - "forward_list"
  - "forward_list/std::forward_list"
  - "std.forward_list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_list クラス"
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# forward_list クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素の可変長シーケンスを制御するオブジェクトを表します。  シーケンスはノードのシングル リンク リストとして格納され、各ノードには型 `Type` のメンバーが含まれます。  
  
## 構文  
  
```  
template<  
    class Type,   
    class Allocator = allocator<Type>   
>  
class forward_list   
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Type`|forward\_list に格納される要素のデータ型。|  
|`Allocator`|forward\_list によるメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクト。  このパラメーターは省略できます。  既定値は allocator\<`Type`\> です。|  
  
## 解説  
 `forward_list` オブジェクトは、[allocator クラス](../standard-library/allocator-class.md) \(一般的な呼び方では `std::allocator)`\) に基づくクラス `Allocator` の格納されているオブジェクトを通じて制御しているシーケンスに対して、ストレージの割り当てと解放を行います。  詳細については、「[アロケーター](../Topic/Allocators.md)」をご覧ください。  アロケーター オブジェクトは、`allocator` テンプレート クラスのオブジェクトと同じ外部インターフェイスを持っている必要があります。  
  
> [!NOTE]
>  コンテナー オブジェクトを代入しても、格納されているアロケーター オブジェクトはコピーされません。  
  
 反復子、ポインター、および参照は、それらの被制御シーケンスの要素が `forward_list` を通じて消去された場合、無効になる可能性があります。  `forward_list` を通じて被制御シーケンスに対して行われた挿入およびスプライスによって反復子が無効になることはありません。  
  
 [forward\_list::insert\_after](../Topic/forward_list::insert_after.md) の呼び出しによって、被制御シーケンスへの追加が発生する場合があります。この関数は、コンストラクター `Type(const _Type&)` を呼び出す唯一のメンバー関数です。  `forward_list` は、移動コンストラクターも呼び出す場合があります。  このような式が例外をスローした場合、コンテナー オブジェクトは新しい要素を挿入せず、例外を再スローします。  したがって、テンプレート クラス `forward_list` のオブジェクトは、このような例外が発生したときに、既知の状態のままになります。  
  
### コンストラクター  
  
|||  
|-|-|  
|[forward\_list](../Topic/forward_list::forward_list.md)|`forward_list` 型のオブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/forward_list::allocator_type.md)|前方リスト オブジェクトのアロケーター クラスを表す型。|  
|[const\_iterator](../Topic/forward_list::const_iterator.md)|前方リストに定数反復子を提供する型。|  
|[const\_pointer](../Topic/forward_list::const_pointer.md)|前方リスト内の `const` 要素へのポインターを提供する型。|  
|[const\_reference](../Topic/forward_list::const_reference.md)|前方リスト内の要素への定数参照を提供する型。|  
|[difference\_type](../Topic/forward_list::difference_type.md)|前方リストの要素の数を、反復子が指す要素の範囲に基づいて表すために使用できる符号付き整数型。|  
|[iterator](../Topic/forward_list::iterator.md)|前方リストの反復子を提供する型。|  
|[ポインター](../Topic/forward_list::pointer.md)|前方リスト内の要素へのポインターを提供する型。|  
|[参照](../Topic/forward_list::reference.md)|前方リスト内の要素への参照を提供する型。|  
|[size\_type](../Topic/forward_list::size_type.md)|2 つの要素間の距離を表す、符号なしの型。|  
|[value\_type](../Topic/forward_list::value_type.md)|前方リストに格納された要素の型を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[assign](../Topic/forward_list::assign.md)|前方リストから要素を消去し、対象の前方リストに新しい要素のセットをコピーします。|  
|[before\_begin](../Topic/forward_list::before_begin.md)|前方リスト内の先頭要素の前の位置を示す反復子を返します。|  
|[begin](../Topic/forward_list::begin.md)|前方リスト内の最初の要素を指す反復子を返します。|  
|[cbefore\_begin](../Topic/forward_list::cbefore_begin.md)|前方リスト内の先頭要素の前の位置を示す定数反復子を返します。|  
|[cbegin](../Topic/forward_list::cbegin.md)|前方リスト内の最初の要素を指す定数反復子を返します。|  
|[cend](../Topic/forward_list::cend.md)|前方リスト内の最後の要素の次の場所を指す定数反復子を返します。|  
|[クリア](../Topic/forward_list::clear.md)|前方リストのすべての要素を消去します。|  
|[emplace\_after](../Topic/forward_list::emplace_after.md)|指定された位置の後に新しい要素を構築します。|  
|[emplace\_front](../Topic/forward_list::emplace_front.md)|イン プレースで構築された要素をリストの先頭に追加します。|  
|[\(なし\)](../Topic/forward_list::empty.md)|前方リストが空であるかどうかをテストします。|  
|[End](../Topic/forward_list::end.md)|前方リスト内の最後の要素の次の場所を指す反復子を返します。|  
|[erase\_after](../Topic/forward_list::erase_after.md)|前方リストから指定された位置の後の要素を削除します。|  
|[front](../Topic/forward_list::front.md)|前方リスト内の最初の要素への参照を返します。|  
|[get\_allocator](../Topic/forward_list::get_allocator.md)|前方リストの構築に使用されるアロケーター オブジェクトのコピーを返します。|  
|[insert\_after](../Topic/forward_list::insert_after.md)|前方リストの指定された位置の後に要素を追加します。|  
|[max\_size](../Topic/forward_list::max_size.md)|前方リストの最大長を返します。|  
|[マージ](../Topic/forward_list::merge.md)|引数リストから要素を削除し、それをターゲットの前方リストに挿入して、新たに組み合わされたセットの要素を昇順またはその他の指定された順序で並べ替えます。|  
|[pop\_front](../Topic/forward_list::pop_front.md)|前方リストの先頭から要素を削除します。|  
|[push\_front](../Topic/forward_list::push_front.md)|前方リストの先頭に要素を追加します。|  
|[削除](../Topic/forward_list::remove.md)|指定された値と一致する前方リスト内の要素を消去します。|  
|[remove\_if](../Topic/forward_list::remove_if.md)|指定された述語を満たす前方リスト内の要素を消去します。|  
|[サイズの変更](../Topic/forward_list::resize.md)|前方リストの新しいサイズを指定します。|  
|[reverse](../Topic/forward_list::reverse.md)|前方リスト内で要素が出現する順序を反転させます。|  
|[sort](../Topic/forward_list::sort.md)|要素を昇順または述語によって指定された順序で配置します。|  
|[splice\_after](../Topic/forward_list::splice_after.md)|ノード間のリンクを再接合します。|  
|[swap](../Topic/forward_list::swap.md)|2 つの前方リストの要素を交換します。|  
|[unique](../Topic/forward_list::unique.md)|指定されたテストに合格した隣接する要素を削除します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/forward_list::operator=.md)|別の前方リストのコピーで前方リストの要素を置き換えます。|  
  
## 必要条件  
 **ヘッダー:** \<forward\_list\>  
  
 **名前空間:** std  
  
## 参照  
 [\<forward\_list\>](../standard-library/forward-list.md)