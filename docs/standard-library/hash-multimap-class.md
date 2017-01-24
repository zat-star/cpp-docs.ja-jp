---
title: "hash_multimap クラス | Microsoft Docs"
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
  - "stdext::hash_multimap"
  - "stdext.hash_multimap"
  - "hash_map/stdext::hash_multimap"
  - "hash_multimap"
  - "std::hash_multimap"
  - "std.hash_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_multimap クラス"
ms.assetid: f41a6db9-67aa-43a3-a3c5-dbfe9ec3ae7d
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hash_multimap クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  この API は、互換性のために残されています。  代わりに、[unordered\_multimap クラス](../standard-library/unordered-multimap-class.md)を使用してください。  
  
 コンテナー クラスの hash\_multimap は、標準テンプレート ライブラリの拡張機能であり、並べ替えキーとデータ値のペアを要素として持つコレクションのデータを格納したり迅速に取得したりするために使用されます。キーの値は一意である必要がありません。  
  
## 構文  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<pair <const Key, Type> >   
>  
class hash_multimap  
```  
  
#### パラメーター  
 `Key`  
 hash\_multimap に格納されるキーのデータ型。  
  
 `Type`  
 hash\_multimap に格納される要素のデータ型。  
  
 `Traits`  
 2 つの関数オブジェクトを含む型。2 つの要素の値を並べ替えキーとして比較し、要素の相対順序を決定できるクラス `Traits` のいずれかと、要素のキー値を型 **size\_t** の符号なし整数にマップする単項述語であるハッシュ関数です。  この引数は省略可能であり、既定値は `hash_compare``<Key, less<Key> >` です。  
  
 `Allocator`  
 メモリの hash\_multimap の割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  この引数は省略可能であり、既定値は `allocator<pair <const Key, Type> >` です。  
  
## 解説  
 hash\_multimap の特徴を次に示します。  
  
-   hash\_map は連想コンテナーであり、関連付けられたキー値に基づいて要素の値を効率的に取得できるようにする可変サイズのコンテナーとして機能します。  
  
-   反転することができます。これは、hash\_map には、要素にアクセスするための双方向反復子が用意されているためです。  
  
-   ハッシュされます。これは、要素のキー値に適用されたハッシュ関数の値に基づいて、要素がバケットにグループ化されるためです。  
  
-   複数対応です。要素は一意のキーを持つ必要がないので、関連する多くの要素データ値を 1 つのキー値が持つことができるためです。  
  
-   ペアを保持する連想コンテナーです。これは、要素値とキー値が分かれているためです。  
  
-   テンプレート クラスとして機能します。これは、このクラスに用意されている機能が汎用的な機能であり、要素またはキーとして保持されているデータの特定の型に依存しないためです。  要素やキーに使用されているデータ型は、クラス テンプレートで比較関数やアロケーターと共にパラメーターとして指定されます。  
  
 並べ替えでのハッシュの主な利点は、効率に優れていることです。コンテナー内にある要素を並べ替えるとき、その時間は要素の数の対数に比例しますが、適切なハッシュを実行すると、挿入、削除、検索にかかる平均時間は一定しています。  hash\_multimap の要素の値 \(関連するキー値ではありません\) は、直接変更できます。  この場合、変更前の要素に関連付けられていたキー値を削除し、新しい要素に関連付けられる新しいキー値を挿入する必要があります。  
  
 一般的に、コンテナー型の選択は、アプリケーションにおいて必要な検索および挿入の種類に基づいている必要があります。  ハッシュされた連想コンテナーは、検索、挿入、削除の各操作用に最適化されています。  これらの操作を明示的にサポートするメンバー関数は、適切に記述されたハッシュ関数と共に使用すると、効率的に機能します。検索、挿入、削除の操作にかかる実行時間は、平均で一定しており、コンテナー内の要素の数による影響を受けません。  適切に記述されたハッシュ関数によって、ハッシュ値の一様分布が生成され、競合の数を最小限に抑えることができます \(競合は、異なるキー値が同じハッシュ値にマップされたときに発生する可能性があります\)。  最悪のケースは、不適切に記述されたハッシュ関数が使用される場合です。演算の回数は、シーケンス内の要素数に比例して増えることになります \(線形時間\)。  
  
 hash\_multimap は、値とキーを関連付ける条件をアプリケーションが満たしている場合、最適な連想コンテナーです。  この種類の構造体のモデルとなるのは、キー ワードとそれに関連する文字列値 \(たとえば定義\) の順序付きリストです。キー ワードは常に一意に定義されるわけではありません。  そうでなくて、キー ワードが一意に定義され、キーが一意になる場合は、hash\_map が最適なコンテナーです。  また、キーワードのリストだけが格納される場合は、hash\_set が適切なコンテナーとなります。  キーワードを複数設定できる場合は、hash\_multiset が適切なコンテナー構造体となります。  
  
 hash\_multimap は、格納されているハッシュ `Traits` オブジェクト \([value\_compare](../Topic/value_compare%20Class.md) 型\) を呼び出すことによって、制御するシーケンスを並べ替えます。  格納されているこのオブジェクトには、メンバー関数 [key\_comp](../Topic/hash_map::key_comp.md) を呼び出すことによってアクセスできます。  このような関数オブジェクトは、[hash\_compare](../standard-library/hash-compare-class.md)`<Key,  less<Key> >` クラスのオブジェクトと同様に動作する必要があります。  具体的には、`Key` 型のすべての `Key` の値に対して、`Traits (Key)` を呼び出すことにより、`size_t` 型の値を配布します。  
  
 通常、要素は、この順序を確立するために小なり比較だけを実行できる必要があります。これにより、2 つの要素が指定されたときに、それらの要素が等しいか \(どちらか一方が小さくはない\)、または一方が他方より小さいかを判断できます。  この結果、等価でない複数の要素間で順序が付けられます。  テクニカル ノートでは、比較関数は、数学上の標準的な意味で厳密弱順序を発生させる二項述語であると示されています。  二項述語 f\(x, y\) は、2 つの引数オブジェクト \(`x` および `y`\) と戻り値 \(`true` または `false`\) を持つ関数オブジェクトです。  hash\_multimap に適用される順序付けは、二項述語が非再帰、反対称、推移的であり、等価性が推移的である \(2 つのオブジェクト `x` と `y` が、f\(x, y\) と f\(y, x\) の両方が `false` の場合に等価になるように定義されている\) 場合、厳密弱順序になります。  2 つのキーの等値に関する条件が等価性の条件よりも厳しく、優先される場合、順序付けは完全な順序付け \(すべての要素が相互の値に基づいて並べ替えられる\) となり、一致するそれぞれのキーを識別するのが難しくなります。  
  
 被制御シーケンスにおける要素の実際の順序は、ハッシュ関数、順序関数、コンテナー オブジェクトに格納されるハッシュ テーブルの現在のサイズによって異なります。  ハッシュ テーブルの現在のサイズは特定できないため、通常は、被制御シーケンス内の要素の順序を予測することはできません。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を具体的に指す反復子だけが無効化されます。  
  
 hash\_multimap クラスに用意されている反復子は双方向反復子ですが、クラス メンバー関数 [insert](../Topic/hash_multimap::insert.md) と [hash\_multimap](../Topic/hash_multimap::hash_multimap.md) には、弱い入力反復子をテンプレート パラメーターとして取得するバージョンがあります。この反復子の機能に関する要件は、双方向反復子のクラスで保証されている要件よりも低くなっています。  これらの反復子の機能に差異があるのは、反復子の概念が異なっているためです。  反復子の各概念には、反復子独自の要件の hash\_multimap が含まれています。また、それらの要件を使用するアルゴリズムでは、反復子の種類ごとに指定されている要件で前提を絞り込む必要があります。  たとえば、一部のオブジェクトを参照するために入力反復子が逆参照される可能性があることを前提とする場合があります。さらに、シーケンス内にある次の反復子に対して逆参照が増加する可能性があることを前提とする場合もあります。  このことは、機能の最小限の hash\_multimap ですが、メンバー関数のコンテキストに含まれる反復子の範囲 `[First, Last)` について明確にするには十分です。  
  
 Visual C\+\+ .NET 2003 では、[\<hash\_map\>](../standard-library/hash-map.md) ヘッダー ファイルと [\<hash\_set\>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。  詳細については、「[The stdext Namespace](../Topic/stdext%20Namespace.md)」を参照してください。  
  
### コンストラクター  
  
|||  
|-|-|  
|[hash\_multimap](../Topic/hash_multimap::hash_multimap.md)|特定のサイズのリスト、特定の値の要素を持つリスト、または特定の `allocator` を持つリストを構築します。あるいは他の `hash_multimap` のコピーとして構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_multimap::allocator_type.md)|`allocator` オブジェクトの `hash_multimap` クラスを表す型。|  
|[const\_iterator](../Topic/hash_multimap::const_iterator.md)|`const` 内の 1 つの `hash_multimap` 要素を読み取ることができる双方向反復子を提供する型。|  
|[const\_pointer](../Topic/hash_multimap::const_pointer.md)|`const` 内の `hash_multimap` 要素へのポインターを提供する型。|  
|[const\_reference](../Topic/hash_multimap::const_reference.md)|読み取りと `const` 操作を実行するために、`hash_multimap` に格納された `const` 要素への参照を提供する型。|  
|[const\_reverse\_iterator](../Topic/hash_multimap::const_reverse_iterator.md)|`const` 内の任意の `hash_multimap` 要素を読み取ることができる双方向反復子を提供する型。|  
|[difference\_type](../Topic/hash_multimap::difference_type.md)|`hash_multimap` の要素の数を、反復子が指す要素の範囲に基づいて表すために使用できる符号付き整数型。|  
|[iterator](../Topic/hash_multimap::iterator.md)|`hash_multimap` 内の任意の要素を読み取り、または変更できる双方向反復子を提供する型。|  
|[key\_compare](../Topic/hash_multimap::key_compare.md)|2 つの並べ替えキーを比較して、`hash_multimap` 内の 2 つの要素の相対順序を決定できる関数オブジェクトを提供する型。|  
|[key\_type](../Topic/hash_multimap::key_type.md)|`hash_multimap` の各要素の一部である並べ替えキー オブジェクトを表す型。|  
|[mapped\_type](../Topic/hash_multimap::mapped_type.md)|`hash_multimap` に格納されているデータ型を表す型。|  
|[ポインター](../Topic/hash_multimap::pointer.md)|`hash_multimap` 内の要素へのポインターを提供する型。|  
|[参照](../Topic/hash_multimap::reference.md)|`hash_multimap` に格納されている要素への参照を提供する型。|  
|[reverse\_iterator](../Topic/hash_multimap::reverse_iterator.md)|反転された `hash_multimap` 内の 1 つの要素を読み取り、または変更できる双方向反復子を提供する型。|  
|[size\_type](../Topic/hash_multimap::size_type.md)|`hash_multimap` 内の要素の数を表すことができる符号なし整数型。|  
|[value\_type](../Topic/hash_multimap::value_type.md)|2 つの要素を並べ替えキーとして比較して、`hash_multimap` 内の要素の相対順序を決定できる関数オブジェクトを提供する型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[begin](../Topic/hash_multimap::begin.md)|`hash_multimap` 内の最初の要素を指す反復子を返します。|  
|[hash\_multimap::cbegin](../Topic/hash_multimap::cbegin.md)|`hash_multimap` 内の最初の要素を指す定数反復子を返します。|  
|[hash\_multimap::cend](../Topic/hash_multimap::cend.md)|`hash_multimap` 内の最後の要素の次の位置を指す定数反復子を返します。|  
|[クリア](../Topic/hash_multimap::clear.md)|`hash_multimap` のすべての要素を消去します。|  
|[count](../Topic/hash_multimap::count.md)|パラメーター指定したキーに一致するキーを持つ、`hash_multimap` 内の要素の数を返します。|  
|[hash\_multimap::crbegin](../Topic/hash_multimap::crbegin.md)|反転された `hash_multimap` 内の最初の要素を指す定数反復子を返します。|  
|[hash\_multimap::crend](../Topic/hash_multimap::crend.md)|反転された `hash_multimap` 内の最後の要素の次の位置を指す定数反復子を返します。|  
|[hash\_multimap::emplace](../Topic/hash_multimap::emplace.md)|インプレースで構築された要素を `hash_multimap` に挿入します。|  
|[hash\_multimap::emplace\_hint](../Topic/hash_multimap::emplace_hint.md)|インプレースで構築された要素を、配置ヒントと共に `hash_multimap` に挿入します。|  
|[\(なし\)](../Topic/hash_multimap::empty.md)|`hash_multimap` が空かどうかをテストします。|  
|[End](../Topic/hash_multimap::end.md)|`hash_multimap` 内の最後の要素の次の位置を指す反復子を返します。|  
|[equal\_range](../Topic/hash_multimap::equal_range.md)|`hash_multimap` 内の最後の要素の次の位置を指す反復子を返します。|  
|[erase](../Topic/hash_multimap::erase.md)|指定した位置から `hash_multimap` 内の要素または要素範囲を削除します。|  
|[find](../Topic/hash_multimap::find.md)|指定したキーと同じキーを持つ、`hash_multimap` 内の要素の位置を指す反復子を返します。|  
|[get\_allocator](../Topic/hash_multimap::get_allocator.md)|`allocator` の構築に使用される `hash_multimap` オブジェクトのコピーを返します。|  
|[挿入](../Topic/hash_multimap::insert.md)|指定した位置において、`hash_multimap` に単一の要素または要素の範囲を挿入します。|  
|[key\_comp](../Topic/hash_multimap::key_comp.md)|`hash_multimap` 内のキーを並べ替えるために使用される比較オブジェクトのコピーを取得します。|  
|[lower\_bound](../Topic/hash_multimap::lower_bound.md)|指定したキー以上のキー値を持つ、`hash_multimap` 内の最初の要素を指す反復子を返します。|  
|[max\_size](../Topic/hash_multimap::max_size.md)|`hash_multimap` の最大長を返します。|  
|[rbegin](../Topic/hash_multimap::rbegin.md)|反転された `hash_multimap` 内の最初の要素を指す反復子を返します。|  
|[rend](../Topic/hash_multimap::rend.md)|反転された `hash_multimap` 内の最後の要素の次の位置を指す反復子を返します。|  
|[size](../Topic/hash_multimap::size.md)|`hash_multimap` の新しいサイズを指定します。|  
|[swap](../Topic/hash_multimap::swap.md)|2 つの `hash_multimap` の要素を交換します。|  
|[upper\_bound](../Topic/hash_multimap::upper_bound.md)|指定したキーよりも大きいキー値を持つ、`hash_multimap` 内の最初の要素を指す反復子を返します。|  
|[value\_comp](../Topic/hash_multimap::value_comp.md)|`hash_multimap` 内の要素の値を並べ替えるために使用される比較オブジェクトのコピーを取得します。|  
  
### 演算子  
  
|||  
|-|-|  
|[hash\_multimap::operator\=](../Topic/hash_multimap::operator=.md)|別の `hash_multimap` のコピーで `hash_multimap` の要素を置き換えます。|  
  
## 必要条件  
 **ヘッダー:** \<hash\_map\>  
  
 **名前空間:** stdext  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)