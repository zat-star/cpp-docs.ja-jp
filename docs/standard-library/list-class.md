---
title: "list クラス | Microsoft Docs"
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
  - "std.list"
  - "list"
  - "std::list"
  - "list/std::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "list クラス"
ms.assetid: d3707f4a-10fd-444f-b856-f9ca2077c1cd
caps.latest.revision: 20
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# list クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL list クラスは、要素を線形の配置に維持し、シーケンス内の任意の場所での効率的な挿入と削除を可能にする、シーケンス コンテナーのテンプレート クラスです。  シーケンスは要素の双方向リンク リストとして格納され、各要素には型 *Type* のメンバーが含まれます。  
  
## 構文  
  
```cpp  
  
template <    class Type,     class Allocator=allocator<Type>  > class list  
```  
  
#### パラメーター  
 *種類*  
 list に格納される要素のデータ型。  
  
 `Allocator`  
 メモリの list の割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  この引数は省略可能であり、既定値は **allocator**\<*Type*\> です。  
  
## 解説  
 一般的に、コンテナー型の選択は、アプリケーションにおいて必要な検索および挿入の種類に基づいている必要があります。  ベクターは、任意の要素へのランダム アクセスが優先事項であり、要素の挿入または削除がシーケンスの最後にのみ必要な場合に、シーケンスを管理するための推奨されるコンテナーです。  クラスの deque コンテナーでは、ランダム アクセスが必要であり、シーケンスの先頭と末尾の両方における挿入と削除が優先事項である場合に、より優れたパフォーマンスになります。  
  
 list のメンバー関数 [merge](../Topic/list::merge.md)、[reverse](../Topic/list::reverse.md)、[unique](../Topic/list::unique.md)、[remove](../Topic/list::remove.md)、および [remove\_if](../Topic/list::remove_if.md) はリスト オブジェクトの操作用に最適化されており、対応する汎用的な関数に比べて、高いパフォーマンスが提供されます。  
  
 リストの再割り当ては、メンバー関数がリストの要素を挿入または消去する必要がある場合に発生します。  このような場合、制御対象シーケンスの消去部分を指す反復子または参照は常に無効になります。  
  
 STL 標準ヘッダー \<list\> を定義するには、[コンテナー](../standard-library/stl-containers.md) テンプレート クラス list および複数のサポート テンプレートをインクルードします。  
  
### コンストラクター  
  
|||  
|-|-|  
|[リスト](../Topic/list::list.md)|特定のサイズのリスト、特定の値の要素を持つリスト、特定の `allocator` を持つリストを構築します。または他のリストのコピーとしてリストを構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[allocator\_type](../Topic/list::allocator_type.md)|リスト オブジェクトの `allocator` クラスを表す型。|  
|[const\_iterator](../Topic/list::const_iterator.md)|リスト内の 1 つの `const` 要素を読み取ることができる双方向反復子を提供する型。|  
|[const\_pointer](../Topic/list::const_pointer.md)|リスト内の `const` 要素へのポインターを提供する型。|  
|[const\_reference](../Topic/list::const_reference.md)|読み取りと `const` 操作の実行のために、リストに格納された `const` 要素への参照を提供する型。|  
|[const\_reverse\_iterator](../Topic/list::const_reverse_iterator.md)|リスト内の任意の `const` 要素を読み取ることができる双方向反復子を提供する型。|  
|[difference\_type](../Topic/list::difference_type.md)|同じリスト内の要素を参照する 2 反復子の違いを提供する型。|  
|[iterator](../Topic/list::iterator.md)|リスト内の任意の要素の読み取りまたは変更ができる双方向反復子を提供する型。|  
|[ポインター](../Topic/list::pointer.md)|リスト内の要素へのポインターを提供する型。|  
|[参照](../Topic/list::reference.md)|読み取りと `const` 操作の実行のために、リストに格納された `const` 要素への参照を提供する型。|  
|[reverse\_iterator](../Topic/list::reverse_iterator.md)|逆順のリスト内の 1 つの要素の読み取りまたは変更ができる双方向反復子を提供する型。|  
|[size\_type](../Topic/list::size_type.md)|リスト内の要素の数をカウントする型。|  
|[value\_type](../Topic/list::value_type.md)|リスト内に格納されているデータ型を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[assign](../Topic/list::assign.md)|リストから要素を消去し、対象のリストに新しい要素のセットをコピーします。|  
|[back](../Topic/list::back.md)|リストの最後の要素への参照を返します。|  
|[begin](../Topic/list::begin.md)|リスト内の最初の要素を指す反復子を返します。|  
|[list::cbegin](../Topic/list::cbegin.md)|リスト内の最初の要素を指す定数反復子を返します。|  
|[list::cend](../Topic/list::cend.md)|リスト内の最後の要素の次の場所を指す定数反復子を返します。|  
|[list::clear](../Topic/list::clear.md)|リストのすべての要素を消去します。|  
|[list::crbegin](../Topic/list::crbegin.md)|逆順のリスト内の最初の要素を指す定数反復子を返します。|  
|[list::crend](../Topic/list::crend.md)|逆順のリスト内の最後の要素の次の位置を指す定数反復子を返します。|  
|[list::emplace](../Topic/list::emplace.md)|指定した位置において、構築された要素をリスト内の適切な場所に挿入します。|  
|[list::emplace\_back](../Topic/list::emplace_back.md)|イン プレースで構築された要素をリストの末尾に追加します。|  
|[list::emplace\_front](../Topic/list::emplace_front.md)|イン プレースで構築された要素をリストの先頭に追加します。|  
|[empty](../Topic/list::empty.md)|リストが空かどうかをテストします。|  
|[End](../Topic/list::end.md)|リスト内の最後の要素の次の位置を指す反復子を返します。|  
|[erase](../Topic/list::erase.md)|指定した位置からリスト内の要素または要素範囲を削除します。|  
|[front](../Topic/list::front.md)|リスト内の最初の要素への参照を返します。|  
|[get\_allocator](../Topic/list::get_allocator.md)|リストの構築に使用される `allocator` オブジェクトのコピーを返します。|  
|[insert](../Topic/list::insert.md)|リストの指定した位置に要素、複数の要素、または要素の範囲を挿入します。|  
|[max\_size](../Topic/list::max_size.md)|リストの最大長を返します。|  
|[merge](../Topic/list::merge.md)|引数リストから要素を削除し、それを対象のリストに挿入して、新たに組み合わされたセットの要素を昇順またはその他の指定された順序で並べ替えます。|  
|[pop\_back](../Topic/list::pop_back.md)|リストの末尾の要素を削除します。|  
|[pop\_front](../Topic/list::pop_front.md)|リストの先頭から要素を削除します。|  
|[push\_back](../Topic/list::push_back.md)|リストの末尾に要素を追加します。|  
|[push\_front](../Topic/list::push_front.md)|リストの先頭に要素を追加します。|  
|[rbegin](../Topic/list::rbegin.md)|逆順のリスト内の最初の要素を指す反復子を返します。|  
|[remove](../Topic/list::remove.md)|指定された値と一致するリストの要素を消去します。|  
|[remove\_if](../Topic/list::remove_if.md)|指定した述語の条件を満たすリストから要素を消去します。|  
|[rend](../Topic/list::rend.md)|逆順のリスト内の最後の要素の次の位置を指す反復子を返します。|  
|[resize](../Topic/list::resize.md)|リストの新しいサイズを指定します。|  
|[reverse](../Topic/list::reverse.md)|要素がリストに出現する順序を反転させます。|  
|[size](../Topic/list::size.md)|リスト内の要素数を返します。|  
|[sort](../Topic/list::sort.md)|リストの要素を、昇順または他の順序関係に従って整列します。|  
|[splice](../Topic/list::splice.md)|引数リストから要素を削除し、それらを対象のリストに挿入します。|  
|[swap](../Topic/list::swap.md)|2 つのリストの要素を交換します。|  
|[unique](../Topic/list::unique.md)|隣接する重複要素、または他のいずれかの二項述語の条件を満たす、隣接する要素をリストから削除します。|  
  
### 演算子  
  
|||  
|-|-|  
|[list::operator\=](../Topic/list::operator=.md)|別のリストのコピーでリストの要素を置き換えます。|  
  
## 必要条件  
 **ヘッダー**: \<list\>  
  
## 参照  
 [\<list\>](../standard-library/list.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)