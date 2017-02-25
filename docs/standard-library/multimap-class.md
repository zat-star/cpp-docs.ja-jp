---
title: "multimap クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "multimap"
  - "std.multimap"
  - "map/std::multimap"
  - "std::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multimap クラス"
ms.assetid: 8796ae05-37c4-475a-9e61-75fde9d4a463
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# multimap クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

標準テンプレート ライブラリの multimap クラスは、各要素がデータ値と並べ替えキーのペアであるコレクションのデータを格納および取得するために使用されます。  キーの値は一意である必要がなく、データを自動的に並べ替えるために使用されます。  multimap の要素の値 \(関連するキー値ではありません\) は、直接変更できます。  この場合、変更前の要素に関連付けられていたキー値を削除し、新しい要素に関連付けられる新しいキー値を挿入する必要があります。  
  
## 構文  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits=less<Key>,   
   class Allocator=allocator<pair <const Key, Type> >   
> class multimap;  
```  
  
#### パラメーター  
 `Key`  
 multimap に格納されるキーのデータ型。  
  
 `Type`  
 multimap に格納される要素のデータ型。  
  
 `Traits`  
 2 つの要素の値を並べ替えキーとして比較して、multimap 内の要素の相対順序を決定できる関数オブジェクトを提供する型。  二項述語 `less<Key>` が既定値です。  
  
 C\+\+ 14 では、型パラメーターを使用せずに `std::less<>` 述語または `std::greater<>` 述語を指定することで、異種ルックアップを有効にすることができます。  詳細については、「[連想コンテナーの異種ルックアップ](../standard-library/stl-containers.md#sequence_containers)」を参照してください。  
  
 `Allocator`  
 メモリの map の割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  この引数は省略可能であり、既定値は `allocator<pair <const Key, Type> >` です。  
  
## 解説  
 STL の multimap クラスの特徴は次のとおりです。  
  
-   hash\_map は連想コンテナーであり、関連付けられたキー値に基づいて要素の値を効率的に取得できるようにする可変サイズのコンテナーとして機能します。  
  
-   反転することができます。これは、要素にアクセスするための双方向反復子が用意されているためです。  
  
-   並べ替えが実行されます。これは、指定した比較関数に従ってコンテナー内のキー値によって要素に順序が設定されるためです。  
  
-   複数対応です。要素は一意のキーを持つ必要がないので、関連する多くの要素データ値を 1 つのキー値が持つことができるためです。  
  
-   ペアを保持する連想コンテナーです。これは、要素のデータ値とキー値が分かれているためです。  
  
-   テンプレート クラスとして機能します。これは、このクラスに用意されている機能が汎用的な機能であり、要素またはキーとして保持されているデータの特定の型に依存しないためです。  要素やキーに使用されているデータ型は、クラス テンプレートで比較関数やアロケーターと共にパラメーターとして指定されます。  
  
 map クラスに用意されている反復子は双方向反復子ですが、クラス メンバー関数 [insert](../Topic/multimap::insert.md) と [multimap](../Topic/multimap::multimap.md) には、弱い入力反復子をテンプレート パラメーターとして取得するバージョンがあります。この反復子の機能に関する要件は、双方向反復子のクラスで保証されている要件よりも低くなっています。  これらの反復子の機能に差異があるのは、反復子の概念が異なっているためです。  反復子の各概念には、反復子独自の一連の要件が含まれています。また、それらの要件を使用するアルゴリズムでは、反復子の種類ごとに指定されている要件に対して、前提を絞り込む必要があります。  たとえば、一部のオブジェクトを参照するために入力反復子が逆参照される可能性があることを前提とする場合があります。さらに、シーケンス内にある次の反復子に対して逆参照が増加する可能性があることを前提とする場合もあります。  このことは、最小限実施することですが、クラスのメンバー関数のコンテキストに含まれる反復子の範囲 `[First, Last)` について明確にすることも重要です。  
  
 一般的に、コンテナー型の選択は、アプリケーションにおいて必要な検索および挿入の種類に基づいている必要があります。  連想コンテナーは、検索、挿入、削除の各操作用に最適化されています。  これらの操作を明示的にサポートするメンバー関数は効率的であり、処理時間は平均的にコンテナー内にある要素の数の対数に比例します。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を具体的に指す反復子だけが無効化されます。  
  
 multimap は、値とキーを関連付ける条件をアプリケーションが満たしている場合、最適な連想コンテナーです。  この種類の構造体のモデルとなるのは、キー ワードとそれに関連する文字列値 \(たとえば定義\) の順序付きリストです。キー ワードは常に一意に定義されるわけではありません。  そうではなくて、キーワードが一意に定義され、キーが一意になる場合は、map が最適なコンテナーです。  また、キーワードのリストだけが格納される場合は、set が適切なコンテナーとなります。  キーワードを複数設定できる場合は、multiset が適切なコンテナー構造体となります。  
  
 multimap では、[key\_compare](../Topic/multimap::key_compare.md) 型の格納されている関数オブジェクトを呼び出すことによって、multimap が制御するシーケンスを並べ替えます。  格納されているこのオブジェクトは比較関数であり、メンバー関数 [key\_comp](../Topic/multimap::key_comp.md) を呼び出すことによってアクセスできます。  通常、要素は、この順序を確立するために小なり比較だけを実行できる必要があります。これにより、2 つの要素が指定されたときに、それらの要素が等しいか \(どちらか一方が小さくはない\)、または一方が他方より小さいかを判断できます。  この結果、等価でない複数の要素間で順序が付けられます。  テクニカル ノートでは、比較関数は、数学上の標準的な意味で厳密弱順序を発生させる二項述語であると示されています。  二項述語 `f(x,y)` は、2 つの引数オブジェクト \(`x` および `y`\) と戻り値 \(true または false\) を持つ関数オブジェクトです。  set に適用される順序付けは、二項述語が非再帰、反対称、推移的であり、等価性が推移的である \(2 つのオブジェクト `x` と `y` が、`f(x,y)` と `f(y,x)` の両方が false の場合に等価になるように定義されている\) 場合、厳密弱順序になります。  2 つのキーの等値に関する条件が等価性の条件よりも厳しく、優先される場合、順序付けは完全な順序付け \(すべての要素が相互の値に基づいて並べ替えられる\) となり、一致するそれぞれのキーを識別するのが難しくなります。  
  
 C\+\+ 14 では、型パラメーターを使用せずに `std::less<>` 述語または `std::greater<>` 述語を指定することで、異種ルックアップを有効にすることができます。  詳細については、「[連想コンテナーの異種ルックアップ](../standard-library/stl-containers.md#sequence_containers)」を参照してください。  
  
## メンバー  
  
### コンストラクター  
  
|||  
|-|-|  
|[multimap](../Topic/multimap::multimap.md)|空の `multimap`、または他の `multimap` の全体または一部のコピーである hash\_multiset を構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/multimap::allocator_type.md)|`allocator` オブジェクトの `multimap` クラスを表す型。|  
|[const\_iterator](../Topic/multimap::const_iterator.md)|`const` 内の 1 つの `multimap` 要素を読み取ることができる双方向反復子を提供する型。|  
|[const\_pointer](../Topic/multimap::const_pointer.md)|`const` 内の `multimap` 要素へのポインターを提供する型。|  
|[const\_reference](../Topic/multimap::const_reference.md)|読み取りと `const` 操作を実行するために、`multimap` に格納された `const` 要素への参照を提供する型。|  
|[const\_reverse\_iterator](../Topic/multimap::const_reverse_iterator.md)|`const` 内の任意の `multimap` 要素を読み取ることができる双方向反復子を提供する型。|  
|[difference\_type](../Topic/multimap::difference_type.md)|`multimap` の要素の数を、反復子が指す要素の範囲に基づいて表すために使用できる符号付き整数型。|  
|[iterator](../Topic/multimap::iterator.md)|同じ `multimap` 内の要素を参照する 2 つの反復子の違いを提供する型。|  
|[key\_compare](../Topic/multimap::key_compare.md)|2 つの並べ替えキーを比較して、`multimap` 内の 2 つの要素の相対順序を決定できる関数オブジェクトを提供する型。|  
|[key\_type](../Topic/multimap::key_type.md)|`multimap` の各要素の一部である並べ替えキー オブジェクトを表す型。|  
|[mapped\_type](../Topic/multimap::mapped_type.md)|`multimap` に格納されているデータ型を表す型。|  
|[ポインター](../Topic/multimap::pointer.md)|`const` 内の `multimap` 要素へのポインターを提供する型。|  
|[参照](../Topic/multimap::reference.md)|`multimap` に格納されている要素への参照を提供する型。|  
|[reverse\_iterator](../Topic/multimap::reverse_iterator.md)|反転された `multimap` 内の 1 つの要素を読み取り、または変更できる双方向反復子を提供する型。|  
|[size\_type](../Topic/multimap::size_type.md)|`const` 内の `multimap` 要素へのポインターを提供する符号なし整数型。|  
|[value\_type](../Topic/multimap::value_type.md)|2 つの要素を並べ替えキーとして比較して、`multimap` 内の要素の相対順序を決定できる関数オブジェクトを提供する型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[begin](../Topic/multimap::begin.md)|`multimap` 内の最初の要素を指す反復子を返します。|  
|[cbegin](../Topic/multimap::cbegin.md)|`multimap` 内の最初の要素を指す定数反復子を返します。|  
|[cend](../Topic/multimap::cend.md)|`multimap` 内の最後の要素の次の位置を指す定数反復子を返します。|  
|[クリア](../Topic/multimap::clear.md)|`multimap` のすべての要素を消去します。|  
|[count](../Topic/multimap::count.md)|パラメーター指定したキーに一致するキーを持つ、`multimap` 内の要素の数を返します。|  
|[crbegin](../Topic/multimap::crbegin.md)|反転された `multimap` 内の最初の要素を指す定数反復子を返します。|  
|[crend](../Topic/multimap::crend.md)|反転された `multimap` 内の最後の要素の次の位置を指す定数反復子を返します。|  
|[emplace](../Topic/multimap::emplace.md)|インプレースで構築された要素を `multimap` に挿入します。|  
|[emplace\_hint](../Topic/multimap::emplace_hint.md)|インプレースで構築された要素を、配置ヒントと共に `multimap` に挿入します。|  
|[\(なし\)](../Topic/multimap::empty.md)|`multimap` が空かどうかをテストします。|  
|[End](../Topic/multimap::end.md)|`multimap` 内の最後の要素の次の位置を指す反復子を返します。|  
|[equal\_range](../Topic/multimap::equal_range.md)|要素のキーが指定された値と一致する要素の範囲を検索します。|  
|[erase](../Topic/multimap::erase.md)|`multimap` 内の要素または要素の範囲を指定した位置から削除するか、または指定したキーと一致する要素を削除します。|  
|[find](../Topic/multimap::find.md)|指定したキーと同じキーを持つ、`multimap` 内の要素の最初の位置を指す反復子を返します。|  
|[get\_allocator](../Topic/multimap::get_allocator.md)|`allocator` の構築に使用される `multimap` オブジェクトのコピーを返します。|  
|[挿入](../Topic/multimap::insert.md)|`multimap` に要素または要素範囲を挿入します。|  
|[key\_comp](../Topic/multimap::key_comp.md)|`multimap` 内のキーを並べ替えるために使用される比較オブジェクトのコピーを取得します。|  
|[lower\_bound](../Topic/multimap::lower_bound.md)|指定したキー以上のキーを持つ、`multimap` 内の最初の要素を指す反復子を返します。|  
|[max\_size](../Topic/multimap::max_size.md)|`multimap` の最大長を返します。|  
|[rbegin](../Topic/multimap::rbegin.md)|反転された `multimap` 内の最初の要素を指す反復子を返します。|  
|[rend](../Topic/multimap::rend.md)|反転された `multimap` 内の最後の要素の次の位置を指す反復子を返します。|  
|[size](../Topic/multimap::size.md)|`multimap` 内の要素数を返します。|  
|[swap](../Topic/multimap::swap.md)|2 つの `multimap` の要素を交換します。|  
|[upper\_bound](../Topic/multimap::upper_bound.md)|指定したキーよりも大きいキーを持つ、`multimap` 内の最初の要素を指す反復子を返します。|  
|[value\_comp](../Topic/multimap::value_comp.md)|このメンバー関数は、キー値の比較によって `multimap` の要素の順序を決定する関数オブジェクトを返します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/multimap::operator=.md)|別の `multimap` のコピーで `multimap` の要素を置き換えます。|  
  
## 必要条件  
 **ヘッダー:** \<map\>  
  
 **名前空間:** std  
  
 \(**key**, **value**\) のペアは、`pair` 型のオブジェクトとして multimap に格納されます。  pair クラスはヘッダー \<utility\> を必要とし、\<map\> によって自動的にインクルードされます。  
  
## 参照  
 [\<map\> Members](http://msdn.microsoft.com/ja-jp/7e8f0bc2-6034-40f6-9d14-76d4cef86308)   
 [コンテナー](../Topic/Containers%20\(Modern%20C++\).md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)