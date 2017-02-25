---
title: "hash_set クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "hash_set/stdext::hash_set"
  - "std::hash_set"
  - "std.hash_set"
  - "stdext::hash_set"
  - "hash_set"
  - "stdext.hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set クラス"
ms.assetid: c765c06e-cbb6-48c2-93ca-d15468eb28d7
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# hash_set クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  この API は、互換性のために残されています。  代わりに、[unordered\_set クラス](../standard-library/unordered-set-class.md)を使用してください。  
  
 コンテナー クラス hash\_set は、標準テンプレート ライブラリ \(STL\) の拡張です。含まれる要素の値が一意で、キー値として機能するコレクションにおいて、データを格納したり迅速に取得したりするために使用されます。  
  
## 構文  
  
```  
template <  
   class Key,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<Key>   
>  
class hash_set  
```  
  
#### パラメーター  
 `Key`  
 hash\_set に格納される要素のデータ型。  
  
 `Traits`  
 2 つの関数オブジェクトを含む型。2 つの要素値を並べ替えキーとして比較してその相対順序を決定できるクラス比較である二項述語と、要素のキー値を **size\_t** 型の符号なし整数にマップするハッシュ関数である単項述語です。  この引数は省略可能です。既定値は `hash_compare`*\<Key,* **less***\<Key\> \>* です。  
  
 `Allocator`  
 メモリの hash\_set の割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  この引数は省略可能であり、既定値は **allocator***\<Key\>* です。  
  
## 解説  
 hash\_set は次のようなものです。  
  
-   hash\_map は連想コンテナーであり、関連付けられたキー値に基づいて要素の値を効率的に取得できるようにする可変サイズのコンテナーとして機能します。  さらに、単純な連想コンテナーです。これは、要素値がキー値であるためです。  
  
-   反転することができます。これは、hash\_map には、要素にアクセスするための双方向反復子が用意されているためです。  
  
-   ハッシュされます。これは、要素のキー値に適用されたハッシュ関数の値に基づいて、要素がバケットにグループ化されるためです。  
  
-   一意のクラスです。これは、各要素が一意のキーを持つ必要があるためです。  hash\_set は単純な連想コンテナーでもあるため、要素も一意です。  
  
-   テンプレート クラスとして機能します。これは、このクラスに用意されている機能が汎用的な機能であり、要素またはキーとして保持されているデータの特定の型に依存しないためです。  要素やキーに使用されているデータ型は、クラス テンプレートで比較関数やアロケーターと共にパラメーターとして指定されます。  
  
 並べ替えでのハッシュの主な利点は、効率に優れていることです。コンテナー内にある要素を並べ替えるとき、その時間は要素の数の対数に比例しますが、適切なハッシュを実行すると、挿入、削除、検索にかかる平均時間は一定しています。  set 内の要素の値は直接変更できません。  代わりに、以前の値を削除し、新しい値の要素を挿入する必要があります。  
  
 一般的に、コンテナー型の選択は、アプリケーションにおいて必要な検索および挿入の種類に基づいている必要があります。  ハッシュされた連想コンテナーは、検索、挿入、削除の各操作用に最適化されています。  これらの操作を明示的にサポートするメンバー関数は、適切に記述されたハッシュ関数と共に使用すると、効率的に機能します。検索、挿入、削除の操作にかかる実行時間は、平均で一定しており、コンテナー内の要素の数による影響を受けません。  適切に記述されたハッシュ関数によって、ハッシュ値の一様分布が生成され、競合の数を最小限に抑えることができます \(競合は、異なるキー値が同じハッシュ値にマップされたときに発生する可能性があります\)。  最悪のケースは、不適切に記述されたハッシュ関数が使用される場合です。演算の回数は、シーケンス内の要素数に比例して増えることになります \(線形時間\)。  
  
 値とキーを関連付ける条件をアプリケーションが満たしている場合、hash\_set は最適な連想コンテナーとなっている必要があります。  hash\_set の要素は一意であり、独自の並べ替えキーとして機能します。  この種類の構造体のモデルは、単語が 1 回だけ出現する可能性がある単語の順序付きのリストです。  キーワードを複数設定できる場合は、hash\_multiset が適切なコンテナー構造体となります。  値が一意のキーワードのリストにアタッチされている必要がある場合、hash\_map がこのデータを格納するのに適切な構造体です。  キーが一意でない場合は、hash\_multimap が最適なコンテナーです。  
  
 hash\_set は、格納されているハッシュ **Traits** オブジェクト \([value\_compare](../Topic/hash_set::value_compare.md) 型\) を呼び出すことによって、制御するシーケンスを並べ替えます。  格納されているこのオブジェクトには、メンバー関数 [key\_comp](../Topic/hash_set::key_comp.md) を呼び出すことによってアクセスできます。  このような関数オブジェクトは、*hash\_compare\<Key, less\<Key\>\> クラスのオブジェクトと同様に動作する必要があります。*具体的には、Key 型のすべての `_Key` の値に対して、Trait \(`_Key`\) の呼び出しは size\_t 型の値の分布になります。  
  
 通常、要素は、この順序を確立するために小なり比較だけを実行できる必要があります。これにより、2 つの要素が指定されたときに、それらの要素が等しいか \(どちらか一方が小さくはない\)、または一方が他方より小さいかを判断できます。  この結果、等価でない複数の要素間で順序が付けられます。  テクニカル ノートでは、比較関数は、数学上の標準的な意味で厳密弱順序を発生させる二項述語であると示されています。  二項述語 *f*\(*x*,*y*\) は、2 つの引数オブジェクト \(x および y\) と戻り値 \(true または false \) を持つ関数オブジェクトです。  hash\_set に適用される順序付けは、二項述語が非再帰、反対称、推移的であり、等価性が推移的である \(2 つのオブジェクト \(*x* と *y*\) が、*f*\(*x*,*y*\) と *f*\(*y*,*x*\) の両方が false の場合に等価になるように定義されている\) 場合、厳密弱順序になります。  2 つのキーの等値に関する条件が等価性の条件よりも厳しく、優先される場合、順序付けは完全な順序付け \(すべての要素が相互の値に基づいて並べ替えられる\) となり、一致するそれぞれのキーを識別するのが難しくなります。  
  
 被制御シーケンスにおける要素の実際の順序は、ハッシュ関数、順序関数、コンテナー オブジェクトに格納されるハッシュ テーブルの現在のサイズによって異なります。  ハッシュ テーブルの現在のサイズは特定できないため、通常は、被制御シーケンス内の要素の順序を予測することはできません。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を具体的に指す反復子だけが無効化されます。  
  
 hash\_set クラスに用意されている反復子は双方向反復子ですが、クラス メンバー関数 [insert](../Topic/hash_set::insert.md) と [hash\_set](../Topic/hash_set::hash_set.md) には、弱い入力反復子をテンプレート パラメーターとして取得するバージョンがあります。この反復子の機能に関する要件は、双方向反復子のクラスで保証されている要件よりも低くなっています。  これらの反復子の機能に差異があるのは、反復子の概念が異なっているためです。  反復子の各概念には、反復子独自の一連の要件が含まれています。また、それらの要件を使用するアルゴリズムでは、反復子の種類ごとに指定されている要件に対して、前提を絞り込む必要があります。  たとえば、一部のオブジェクトを参照するために入力反復子が逆参照される可能性があることを前提とする場合があります。さらに、シーケンス内にある次の反復子に対して逆参照が増加する可能性があることを前提とする場合もあります。  このことは、最小限実施することですが、クラス メンバー関数のコンテキストに含まれる反復子の範囲 \[`_First`, `_Last`\) について明確にすることも重要です。  
  
 Visual C\+\+ .NET 2003 では、[\<hash\_map\>](../standard-library/hash-map.md) ヘッダー ファイルと [\<hash\_set\>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。  詳細については、「[The stdext Namespace](../Topic/stdext%20Namespace.md)」を参照してください。  
  
### コンストラクター  
  
|||  
|-|-|  
|[hash\_set](../Topic/hash_set::hash_set.md)|空の `hash_set`、または他の `hash_set` の全体または一部のコピーである hash\_multiset を構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_set::allocator_type.md)|`allocator` オブジェクトの `hash_set` クラスを表す型。|  
|[const\_iterator](../Topic/hash_set::const_iterator.md)|`const` 内の 1 つの `hash_set` 要素を読み取ることができる双方向反復子を提供する型。|  
|[const\_pointer](../Topic/hash_set::const_pointer.md)|`const` 内の `hash_set` 要素へのポインターを提供する型。|  
|[const\_reference](../Topic/hash_set::const_reference.md)|読み取りと `const` 操作を実行するために、`hash_set` に格納された `const` 要素への参照を提供する型。|  
|[const\_reverse\_iterator](../Topic/hash_set::const_reverse_iterator.md)|`const` 内の任意の `hash_set` 要素を読み取ることができる双方向反復子を提供する型。|  
|[difference\_type](../Topic/hash_set::difference_type.md)|`hash_set` の要素の数を、反復子が指す要素の範囲に基づいて表すために使用できる符号付き整数型。|  
|[iterator](../Topic/hash_set::iterator.md)|`hash_set` 内の任意の要素を読み取り、または変更できる双方向反復子を提供する型。|  
|[key\_compare](../Topic/hash_set::key_compare.md)|2 つの並べ替えキーを比較して、`hash_set` 内の 2 つの要素の相対順序を決定できる関数オブジェクトを提供する型。|  
|[key\_type](../Topic/hash_set::key_type.md)|並べ替えキーとしてキャパシティ内に `hash_set` の要素として格納されるオブジェクトを表す型。|  
|[ポインター](../Topic/hash_set::pointer.md)|`hash_set` 内の要素へのポインターを提供する型。|  
|[参照](../Topic/hash_set::reference.md)|`hash_set` に格納されている要素への参照を提供する型。|  
|[reverse\_iterator](../Topic/hash_set::reverse_iterator.md)|反転された `hash_set` 内の 1 つの要素を読み取り、または変更できる双方向反復子を提供する型。|  
|[size\_type](../Topic/hash_set::size_type.md)|`hash_set` 内の要素の数を表すことができる符号なし整数型。|  
|[value\_compare](../Topic/hash_set::value_compare.md)|2 つの関数オブジェクト、すなわち、`hash_set` の 2 つの要素の値を比較してその相対順序を判断できるクラス比較の二項述語と、要素のハッシュを計算する単項述語を提供する型です。|  
|[value\_type](../Topic/hash_set::value_type.md)|値としてキャパシティ内に `hash_set` の要素として格納されるオブジェクトを表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[begin](../Topic/hash_set::begin.md)|`hash_set` 内の最初の要素を指す反復子を返します。|  
|[hash\_set::cbegin](../Topic/hash_set::cbegin.md)|`hash_set` 内の最初の要素を指す定数反復子を返します。|  
|[hash\_set::cend](../Topic/hash_set::cend.md)|`hash_set` 内の最後の要素の次の位置を指す定数反復子を返します。|  
|[クリア](../Topic/hash_set::clear.md)|`hash_set` のすべての要素を消去します。|  
|[count](../Topic/hash_set::count.md)|パラメーター指定したキーに一致するキーを持つ、`hash_set` 内の要素の数を返します。|  
|[hash\_set::crbegin](../Topic/hash_set::crbegin.md)|反転された `hash_set` 内の最初の要素を指す定数反復子を返します。|  
|[hash\_set::crend](../Topic/hash_set::crend.md)|反転された `hash_set` 内の最後の要素の次の位置を指す定数反復子を返します。|  
|[hash\_set::emplace](../Topic/hash_set::emplace.md)|インプレースで構築された要素を `hash_set` に挿入します。|  
|[hash\_set::emplace\_hint](../Topic/hash_set::emplace_hint.md)|インプレースで構築された要素を、配置ヒントと共に `hash_set` に挿入します。|  
|[\(なし\)](../Topic/hash_set::empty.md)|`hash_set` が空かどうかをテストします。|  
|[End](../Topic/hash_set::end.md)|`hash_set` 内の最後の要素の次の位置を指す反復子を返します。|  
|[equal\_range](../Topic/hash_set::equal_range.md)|指定したキーよりも大きいキーを持つ、`hash_set` 内の最初の要素を指す反復子と、およびそのキー以上のキーを持つ、`hash_set` 内の最初の要素を指す反復子のペアを返します。|  
|[erase](../Topic/hash_set::erase.md)|`hash_set` 内の要素または要素の範囲を指定した位置から削除するか、または指定したキーと一致する要素を削除します。|  
|[find](../Topic/hash_set::find.md)|指定したキーと同じキーを持つ、`hash_set` 内の要素の位置を指す反復子を返します。|  
|[get\_allocator](../Topic/hash_set::get_allocator.md)|`allocator` の構築に使用される `hash_set` オブジェクトのコピーを返します。|  
|[挿入](../Topic/hash_set::insert.md)|`hash_set` に要素または要素範囲を挿入します。|  
|[key\_comp](../Topic/hash_set::key_comp.md)|`hash_set` 内のキーを並べ替えるために使用される比較オブジェクトのコピーを取得します。|  
|[lower\_bound](../Topic/hash_set::lower_bound.md)|指定したキー以上のキーを持つ、`hash_set` 内の最初の要素を指す反復子を返します。|  
|[max\_size](../Topic/hash_set::max_size.md)|`hash_set` の最大長を返します。|  
|[rbegin](../Topic/hash_set::rbegin.md)|反転された `hash_set` 内の最初の要素を指す反復子を返します。|  
|[rend](../Topic/hash_set::rend.md)|反転された `hash_set` 内の最後の要素の次の位置を指す反復子を返します。|  
|[size](../Topic/hash_set::size.md)|`hash_set` 内の要素数を返します。|  
|[swap](../Topic/hash_set::swap.md)|2 つの `hash_set` の要素を交換します。|  
|[upper\_bound](../Topic/hash_set::upper_bound.md)|指定したキー以上のキーを持つ、`hash_set` 内の最初の要素を指す反復子を返します。|  
|[value\_comp](../Topic/hash_set::value_comp.md)|`hash_set` の要素キー値をハッシュおよび順序付けするために使用するハッシュ特性オブジェクトのコピーを取得します。|  
  
### 演算子  
  
|||  
|-|-|  
|[hash\_set::operator\=](../Topic/hash_set::operator=.md)|別の `hash_set` のコピーで `hash_set` の要素を置き換えます。|  
  
## 必要条件  
 **ヘッダー:** \<hash\_set\>  
  
 **名前空間:** stdext  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)