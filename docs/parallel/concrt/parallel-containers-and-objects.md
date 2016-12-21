---
title: "並列コンテナーと並列オブジェクト | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "並列オブジェクト"
  - "並列コンテナー"
  - "同時実行コンテナー"
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
caps.latest.revision: 34
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 並列コンテナーと並列オブジェクト
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

並列パターン ライブラリ (PPL) には、いくつかのコンテナーとその要素へのスレッド セーフなアクセスを提供するオブジェクトが含まれています。  
  
 A *同時実行コンテナー* 最も重要な操作への同時実行セーフなアクセスを提供します。 これらのコンテナーの機能では、標準テンプレート ライブラリ (STL) によって提供されるものと似ています。 たとえば、 [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) クラスに似ています、 [std::vector](../../standard-library/vector-class.md) クラスのことを除いて、 `concurrent_vector` クラスでは、並列で要素を追加することができます。 読み取りおよび同じコンテナーに対する書き込みアクセスの両方を必要とする並列コードがある場合は、同時実行コンテナーを使用します。  
  
 A *同時実行オブジェクト* はコンポーネント間で同時に共有します。 並列で同時実行オブジェクトの状態を計算するプロセスは、逐次的に同じ状態を計算する別のプロセスと同じ結果を生成します。  [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) クラスは同時実行オブジェクトの種類の一例です。  `combinable` クラスでは、並列で計算を実行して、最終的な結果にその計算を結合することができます。 共有変数またはリソースへのアクセスを同期する同期メカニズム、たとえば、ミュー テックスを使用するとそれ以外の場合とは、同時実行オブジェクトを使用します。  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> セクション  
 このトピックでは、次の並列コンテナーとオブジェクトの詳細について説明します。  
  
 同時実行コンテナー:  
  
-   [concurrent_vector クラス](#vector)  
  
    -   [Concurrent_vector の違いとベクター](#vector-differences)  
  
    -   [同時実行セーフな操作](#vector-safety)  
  
    -   [例外の安全性](#vector-exceptions)  
  
-   [concurrent_queue クラス](#queue)  
  
    -   [Concurrent_queue の違いとキュー](#queue-differences)  
  
    -   [同時実行セーフな操作](#queue-safety)  
  
    -   [反復子のサポート](#queue-iterators)  
  
-   [concurrent_unordered_map クラス](#unordered_map)  
  
    -   [Concurrent_unordered_map の違いと unordered_map](#map-differences)  
  
    -   [同時実行セーフな操作](#map-safety)  
  
-   [concurrent_unordered_multimap クラス](#unordered_multimap)  
  
-   [concurrent_unordered_set クラス](#unordered_set)  
  
-   [concurrent_unordered_multiset クラス](#unordered_multiset)  
  
 同時実行オブジェクト:  
  
-   [combinable クラス](#combinable)  
  
    -   [メソッドと機能](#combinable-features)  
  
    -   [例](#combinable-examples)  
  
##  <a name="a-namevectora-concurrentvector-class"></a><a name="vector"></a> concurrent_vector クラス  
  [Concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) クラスは、シーケンス コンテナー クラスと同じようにする、 [std::vector](../../standard-library/vector-class.md) クラス、その要素にランダムにアクセスすることができます。  `concurrent_vector` クラスを使用する同時実行セーフの追加と要素の操作にアクセスします。 追加の操作では、無効または反復子の既存のポインター。 反復子アクセス、走査の各操作は、同時実行セーフではまたです。  
  
###  <a name="a-namevector-differencesa-differences-between-concurrentvector-and-vector"></a><a name="vector-differences"></a> Concurrent_vector の違いとベクター  
  `concurrent_vector` によく似たクラス、 `vector` クラスです。 追加、要素へのアクセス、および反復子アクセス操作の複雑さ、 `concurrent_vector` オブジェクトが同じである、 `vector` オブジェクトです。 次の点を説明 where `concurrent_vector` とは異なります `vector`:  
  
-   追加、要素へのアクセス、反復子アクセス、反復子走査の各操作で、 `concurrent_vector` オブジェクトは、同時実行セーフです。  
  
-   要素を追加するにはの末尾にのみ、 `concurrent_vector` オブジェクトです。  `concurrent_vector` クラスを提供しない、 `insert` メソッドです。  
  
-   A `concurrent_vector` オブジェクトが使用しない [移動セマンティクス](../../cpp/rvalue-reference-declarator-amp-amp.md) に追加するとします。  
  
-    `concurrent_vector` クラスを提供しない、 `erase` または `pop_back` メソッドです。 同様に `vector`, を使用して、 [オフ](../Topic/concurrent_vector::clear%20Method.md) からすべての要素を削除する方法、 `concurrent_vector` オブジェクトです。  
  
-    `concurrent_vector` クラスはその要素連続してメモリに格納しません。 したがって、使用することはできません、 `concurrent_vector` 配列を使用できるすべての方法でクラスです。 たとえば、という名前の変数 `v` 型の `concurrent_vector`, 、式 `&v[0]+2` 未定義の動作が生成されます。  
  
-    `concurrent_vector` クラスを定義、 [grow_by](../Topic/concurrent_vector::grow_by%20Method.md) と [grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md) メソッドです。 これらのメソッドのように、 [サイズを変更する](../Topic/concurrent_vector::resize%20Method.md) メソッドが、同時実行セーフです。  
  
-   A `concurrent_vector` を追加またはサイズを変更するときに、オブジェクトがその要素を移動できません。 これにより、既存のポインターと同時実行操作中は有効なままを指す反復子。  
  
-   ランタイムはの特殊化バージョンを定義していない `concurrent_vector` タイプの `bool`です。  
  
###  <a name="a-namevector-safetya-concurrency-safe-operations"></a><a name="vector-safety"></a> 同時実行セーフな操作  
 追加またはのサイズが増加するすべてのメソッド、 `concurrent_vector` オブジェクト、または要素にアクセスするには `concurrent_vector` オブジェクトでは、同時実行セーフです。 このルールの例外は、 `resize` メソッドです。  
  
 次の表に、一般的な `concurrent_vector` メソッドと同時実行セーフである演算子。  
  
||||  
|-|-|-|  
|[で](../Topic/concurrent_vector::at%20Method.md)|[終了](../Topic/concurrent_vector::end%20Method.md)|[演算子 & #91、#93 です。](../Topic/concurrent_vector::operatorOperator.md)|  
|[開始](../Topic/concurrent_vector::begin%20Method.md)|[前面](../Topic/concurrent_vector::front%20Method.md)|[push_back](../Topic/concurrent_vector::push_back%20Method.md)|  
|[戻る](../Topic/concurrent_vector::back%20Method.md)|[grow_by](../Topic/concurrent_vector::grow_by%20Method.md)|[rbegin](../Topic/concurrent_vector::rbegin%20Method.md)|  
|[容量](../Topic/concurrent_vector::capacity%20Method.md)|[grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|[rend](../Topic/concurrent_vector::rend%20Method.md)|  
|[空](../Topic/concurrent_vector::empty%20Method.md)|[max_size](../Topic/concurrent_vector::max_size%20Method.md)|[サイズ](../Topic/concurrent_vector::size%20Method.md)|  
  
 操作のランタイムは、STL と互換性のためなどが提供する `reserve`, 、同時実行セーフではありません。 次の表は、共通のメソッドと同時実行セーフではない演算子を示します。  
  
|||  
|-|-|  
|[割り当てる](../Topic/concurrent_vector::assign%20Method.md)|[予約](../Topic/concurrent_vector::reserve%20Method.md)|  
|[オフ](../Topic/concurrent_vector::clear%20Method.md)|[サイズを変更します。](../Topic/concurrent_vector::resize%20Method.md)|  
|[演算子 =](../Topic/concurrent_vector::operator=%20Operator.md)|[shrink_to_fit](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|  
  
 既存の要素の値を変更する操作は、同時実行セーフではありません。 同期オブジェクトを使用して、 [reader_writer_lock](../Topic/reader_writer_lock%20Class.md) を同時読み取りを同期し、同じデータ要素への書き込み操作するオブジェクト。 同期オブジェクトに関する詳細については、次を参照してください。 [同期データ構造](../Topic/Synchronization%20Data%20Structures.md)します。  
  
 使用する既存のコードを変換する `vector` を使用する `concurrent_vector`, 、同時操作を変更するアプリケーションの動作が発生することができます。 たとえば、次のプログラムを同時に 2 つのタスクを実行する、 `concurrent_vector` オブジェクトです。 最初のタスクに追加の要素を追加する、 `concurrent_vector` オブジェクトです。 2 番目のタスクは、同じオブジェクト内のすべての要素の合計を計算します。  
  
 [!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_1.cpp)]  
  
 ただし、 `end` メソッドは同時実行セーフへの同時呼び出し、 [push_back](../Topic/concurrent_vector::push_back%20Method.md) メソッドによって返される値は、 `end` を変更します。 反復子を通過する要素の数は予測できません。 そのため、このプログラムになるは、異なる結果を実行するたびにあります。  
  
###  <a name="a-namevector-exceptionsa-exception-safety"></a><a name="vector-exceptions"></a> 例外の安全性  
 増加率または割り当て操作の状態、例外をスロー、 `concurrent_vector` オブジェクトは無効になります。 動作、 `concurrent_vector` 特に明記しない限り、無効な状態になっているオブジェクトに定義されていません。 ただし、デストラクターでは常にオブジェクトによって割り当てられるメモリを解放して、オブジェクトが無効な状態である場合でもします。  
  
 ベクターの要素のデータ型 `T`, 、次の要件を満たす必要があります。 それ以外の場合の動作、 `concurrent_vector` クラスは未定義です。  
  
-   デストラクターをスローする必要があります。  
  
-   既定値またはコピー コンス トラクターをスローする場合、デストラクター宣言できませんを使用して、 `virtual` キーワードとその必要があります、メモリの量がゼロ初期化正しく動作します。  
  
 [[トップ](#top)]  
  
##  <a name="a-namequeuea-concurrentqueue-class"></a><a name="queue"></a> concurrent_queue クラス  
  [Concurrency::concurrent_queue](../Topic/concurrent_queue%20Class.md) クラスと同じように、 [std::queue](../../standard-library/queue-class.md) クラス、その前にアクセスしたり、要素をバックアップすることができます。  `concurrent_queue` クラスにより同時実行セーフのエンキューおよびデキューします。  `concurrent_queue` クラスは同時実行セーフではない反復子のサポートも提供します。  
  
###  <a name="a-namequeue-differencesa-differences-between-concurrentqueue-and-queue"></a><a name="queue-differences"></a> Concurrent_queue の違いとキュー  
  `concurrent_queue` によく似たクラス、 `queue` クラスです。 次の点を説明 where `concurrent_queue` とは異なります `queue`:  
  
-   キューの操作をキューから削除し、 `concurrent_queue` オブジェクトは、同時実行セーフです。  
  
-    `concurrent_queue` クラスは同時実行セーフではない反復子のサポートを提供します。  
  
-    `concurrent_queue` クラスを提供しない、 `front` または `pop` メソッドです。  `concurrent_queue` クラスが定義することでこれらのメソッドを置き換える、 [try_pop](../Topic/concurrent_queue::try_pop%20Method.md) メソッドです。  
  
-    `concurrent_queue` クラスを提供しない、 `back` メソッドです。 したがって、キューの最後を参照することはできません。  
  
-    `concurrent_queue` クラスには、 [unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md) メソッドの代わりに、 `size` メソッドです。  `unsafe_size` メソッドは同時実行セーフではありません。  
  
###  <a name="a-namequeue-safetya-concurrency-safe-operations"></a><a name="queue-safety"></a> 同時実行セーフな操作  
 すべてのメソッドにエンキューするからデキューしたり、 `concurrent_queue` オブジェクトは、同時実行セーフです。  
  
 次の表に、一般的な `concurrent_queue` メソッドと同時実行セーフである演算子。  
  
|||  
|-|-|  
|[空](../Topic/concurrent_queue::empty%20Method.md)|[プッシュ](../Topic/concurrent_queue::push%20Method.md)|  
|[get_allocator](../Topic/concurrent_queue::get_allocator%20Method.md)|[try_pop](../Topic/concurrent_queue::try_pop%20Method.md)|  
  
 ですが、 `empty` メソッドは同時実行セーフ、同時実行操作を拡大または縮小する前にキューが発生する可能性があります、 `empty` メソッドを返します。  
  
 次の表は、共通のメソッドと同時実行セーフではない演算子を示します。  
  
|||  
|-|-|  
|[オフ](../Topic/concurrent_queue::clear%20Method.md)|[unsafe_end](../Topic/concurrent_queue::unsafe_end%20Method.md)|  
|[unsafe_begin](../Topic/concurrent_queue::unsafe_begin%20Method.md)|[unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md)|  
  
###  <a name="a-namequeue-iteratorsa-iterator-support"></a><a name="queue-iterators"></a> 反復子のサポート  
  `concurrent_queue` 同時実行セーフではない反復子を提供します。 デバッグの場合のみにこれらの反復子を使用することをお勧めします。  
  
 A `concurrent_queue` 反復子が順方向のみに要素を走査します。 次の表では、各反復子をサポートしている演算子を示します。  
  
|演算子|説明|  
|--------------|-----------------|  
|[+ + 演算子](http://msdn.microsoft.com/ja-jp/4cfdd07e-927a-42f8-aaa0-d6881687f413)|キュー内の次の項目に進みます。 この演算子がオーバー ロード、前のインクリメントと後置インクリメントの両方のセマンティクスを提供します。|  
|[演算子 *](http://msdn.microsoft.com/ja-jp/a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|現在の項目への参照を取得します。|  
|[-> 演算子](http://msdn.microsoft.com/ja-jp/41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|現在の項目へのポインターを取得します。|  
  
 [[トップ](#top)]  
  
##  <a name="a-nameunorderedmapa-concurrentunorderedmap-class"></a><a name="unordered_map"></a> concurrent_unordered_map クラス  
  [HYPERLINK"file:///C:\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default\\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622"concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) クラスは、保持する連想コンテナー クラスと同じようにする、 [std::unordered_map](../../standard-library/unordered-map-class.md) クラス、型の要素の可変長シーケンスを制御 [std::pair \< const キー、Ty >](../../standard-library/pair-structure.md)します。 順序なしのマップをキーと値のペアを追加したり、キーに値を参照するディクショナリと考えます。 このクラスは、複数のスレッドまたは同時に共有のコンテナーへのアクセスを挿入して、または更新する必要があるタスクがある場合に便利です。  
  
 次の例を使用するための基本的な構造を示しています。 `concurrent_unordered_map`します。 この例では、["a"、' i'] の範囲の文字のキーを挿入します。 操作の順序が決定されるため、各キーの最終的な値も不定です。 ただし、並列で、挿入の実行にも安全です。  
  
 [!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_2.cpp)]  
  
 使用例について `concurrent_unordered_map` マップを実行し、並列操作の低減を参照してください。 [する方法: 実行のマップと削減の操作を並列](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)します。  
  
###  <a name="a-namemap-differencesa-differences-between-concurrentunorderedmap-and-unorderedmap"></a><a name="map-differences"></a> Concurrent_unordered_map の違いと unordered_map  
  `concurrent_unordered_map` によく似たクラス、 `unordered_map` クラスです。 次の点を説明 where `concurrent_unordered_map` とは異なります `unordered_map`:  
  
-    `erase`, 、`bucket`, 、`bucket_count`, 、および `bucket_size` メソッドの名前として `unsafe_erase`, 、`unsafe_bucket`, 、`unsafe_bucket_count`, 、および `unsafe_bucket_size`, 、それぞれします。  `unsafe_` 名前付け規則では、これらのメソッドは同時実行セーフではないことを示します。 同時実行の安全性の詳細については、次を参照してください。 [同時実行セーフな操作](#map-safety)します。  
  
-   挿入操作が既存のポインターまたは反復子、無効にされません。 また、マップに既に存在する項目の順序を変更しないでください。 挿入し、スキャン操作が同時に発生することができます。  
  
-   `concurrent_unordered_map` サポートは、イテレーションのみを転送します。  
  
-   カーソルが無効にしたりによって返される反復子を更新していない `equal_range`します。 カーソルは、範囲の末尾に等しくない項目を追加できます。 Begin 反復子は、同じ項目を指します。  
  
 メソッドを含まないデッドロックを回避する `concurrent_unordered_map` メモリ アロケーター、ハッシュ関数、またはその他のユーザー定義コードを呼び出すときにロックを保持します。 また、ハッシュ関数が同じ値に等しいキーを常に評価されたことを確認する必要があります。 最適なハッシュ関数は、ハッシュ コードの領域間で一様にキーを配布します。  
  
###  <a name="a-namemap-safetya-concurrency-safe-operations"></a><a name="map-safety"></a> 同時実行セーフな操作  
  `concurrent_unordered_map` クラスは、同時実行セーフの挿入や要素へのアクセスの操作を使用します。 挿入操作には、既存のポインターまたは反復子は無効にしないでください。 反復子アクセス、走査の各操作は、同時実行セーフではまたです。 次の表は、一般的に使用される `concurrent_unordered_map` メソッドと同時実行セーフである演算子。  
  
|||||  
|-|-|-|-|  
|[で](../Topic/concurrent_unordered_map::at%20Method.md)|`count`|`find`|[key_eq](../Topic/concurrent_unordered_map::key_eq%20Method.md)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[演算子 & #91、#93 です。](../Topic/concurrent_unordered_map::operatorOperator.md)|  
|`cend`|`equal_range`|[挿入](../Topic/concurrent_unordered_map::insert%20Method.md)|`size`|  
  
 ですが、 `count` からスレッドを同時に実行するメソッドを安全に呼び出すことが、場合に、コンテナーに新しい値が挿入される同時に、別のスレッドは異なる結果を受信できます。  
  
 次の表は、一般的に使用されるメソッドと同時実行セーフではない演算子を示します。  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[演算子 =](../Topic/concurrent_unordered_map::operator=%20Operator.md)|[スワップ](../Topic/concurrent_unordered_map::swap%20Method.md)|  
  
 これらのメソッドだけでなく任意の方法で始まる `unsafe_` もは同時実行セーフにありません。  
  
 [[トップ](#top)]  
  
##  <a name="a-nameunorderedmultimapa-concurrentunorderedmultimap-class"></a><a name="unordered_multimap"></a> concurrent_unordered_multimap クラス  
  [Concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) によく似たクラス、 `concurrent_unordered_map` クラスの同じキーにマップする複数の値を許可する点が異なります。 異なります `concurrent_unordered_map` 次のようにします。  
  
-    [Concurrent_unordered_multimap::insert](../Topic/concurrent_unordered_multimap::insert%20Method.md) メソッドの代わりに反復子を返します `std::pair<iterator, bool>`します。  
  
-    `concurrent_unordered_multimap` クラスを提供しない `operator[]` も `at` メソッドです。  
  
 次の例を使用するための基本的な構造を示しています。 `concurrent_unordered_multimap`します。 この例では、["a"、' i'] の範囲の文字のキーを挿入します。 `concurrent_unordered_multimap` 複数の値がキーを使用できます。  
  
 [!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_3.cpp)]  
  
 [[トップ](#top)]  
  
##  <a name="a-nameunorderedseta-concurrentunorderedset-class"></a><a name="unordered_set"></a> concurrent_unordered_set クラス  
  [Concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) によく似たクラス、 `concurrent_unordered_map` クラスのキーと値のペアではなく値を管理する点が異なります。  `concurrent_unordered_set` クラスを提供しない `operator[]` も `at` メソッドです。  
  
 次の例を使用するための基本的な構造を示しています。 `concurrent_unordered_set`します。 この例では、["a"、' i'] の範囲の文字の値を挿入します。 並列で、挿入の実行にも安全です。  
  
 [!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_4.cpp)]  
  
 [[トップ](#top)]  
  
##  <a name="a-nameunorderedmultiseta-concurrentunorderedmultiset-class"></a><a name="unordered_multiset"></a> concurrent_unordered_multiset クラス  
  [Concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) によく似たクラス、 `concurrent_unordered_set` クラスの重複する値を許可する点が異なります。 異なります `concurrent_unordered_set` 次のようにします。  
  
-    [Concurrent_unordered_multiset::insert](../Topic/concurrent_unordered_multiset::insert%20Method.md) メソッドの代わりに反復子を返します `std::pair<iterator, bool>`します。  
  
-    `concurrent_unordered_multiset` クラスを提供しない `operator[]` も `at` メソッドです。  
  
 次の例を使用するための基本的な構造を示しています。 `concurrent_unordered_multiset`します。 この例では、["a"、' i'] の範囲の文字の値を挿入します。 `concurrent_unordered_multiset` 複数回出現する値を有効にします。  
  
 [!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_5.cpp)]  
  
 [[トップ](#top)]  
  
##  <a name="a-namecombinablea-combinable-class"></a><a name="combinable"></a> combinable クラス  
  [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) クラスには、再利用可能なスレッド ローカル ストレージを使用して、詳細な計算を実行し、その後、その計算を最終結果にマージするが用意されています。 `combinable` オブジェクトは減少変数と考えることができます。  
  
  `combinable` クラスは、いくつかのスレッドやタスク間で共有されているリソースが存在する場合に便利です。  `combinable` クラスを使用して、ロック制御不要の方法で共有リソースへのアクセスを提供することで共有状態を回避できます。 そのため、このクラスは、複数のスレッドから共有データへのアクセスを同期する同期メカニズム、たとえば、ミュー テックスを使用する代わりを提供します。  
  
###  <a name="a-namecombinable-featuresa-methods-and-features"></a><a name="combinable-features"></a> メソッドと機能  
 次の表にはいくつかの重要なメソッドの `combinable` クラスです。 すべての詳細については、 `combinable` クラスのメソッドを参照してください [combinable クラス](../../parallel/concrt/reference/combinable-class.md)します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[ローカル](../Topic/combinable::local%20Method.md)|現在のスレッド コンテキストに関連付けられているローカル変数への参照を取得します。|  
|[オフ](../Topic/combinable::clear%20Method.md)|すべてのスレッド ローカル変数を削除、 `combinable` オブジェクトです。|  
|[結合](../Topic/combinable::combine%20Method.md)<br /><br /> [combine_each](../Topic/combinable::combine_each%20Method.md)|指定された結合関数を使用して、すべてのスレッド ローカル計算のセットから最終的な値を生成します。|  
  
  `combinable` クラスは、最終的なマージされた結果でパラメーター化されたテンプレート クラス。 既定のコンス トラクターを呼び出す場合、 `T` テンプレート パラメーターの型は、既定のコンス トラクターとコピー コンス トラクターを持つ必要があります。 場合、 `T` テンプレート パラメーター型には、既定のコンス トラクターはありません。 をパラメーターとして初期化関数を受け取るコンス トラクターのオーバー ロードされたバージョンを呼び出します。  
  
 内の他のデータを格納する、 `combinable` オブジェクトを呼び出した後、 [結合](../Topic/combinable::combine%20Method.md) または [combine_each](../Topic/combinable::combine_each%20Method.md) メソッドです。 呼び出すことも、 `combine` と `combine_each` 複数回のメソッドです。 場合にローカルの値はありません、 `combinable` オブジェクトに対する変更を `combine` と `combine_each` メソッドが呼び出されるたびに同じ結果を生成します。  
  
###  <a name="a-namecombinable-examplesa-examples"></a><a name="combinable-examples"></a> 例  
 例については、使用する方法について、 `combinable` 、次のトピックを参照してください。  
  
-   [方法: パフォーマンスを改善する combinable を使用して](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [方法: 集合を結合する combinable を使用して](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[トップ](#top)]  
  
## <a name="related-topics"></a>関連トピック  
 [方法: 並列コンテナーを使用して効率を向上させる](../Topic/How%20to:%20Use%20Parallel%20Containers%20to%20Increase%20Efficiency.md)  
 並列コンテナーを使用して効率的に格納し、並列のデータにアクセスする方法を示します。  
  
 [方法: パフォーマンスを改善する combinable を使用して](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 使用する方法を示しています、 `combinable` クラスの共有状態を解消して、パフォーマンスが向上します。  
  
 [方法: 集合を結合する combinable を使用して](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 使用する方法を示しています、 `combine` データのスレッド ローカルな集合を結合する関数。  
  
 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 スケーラビリティと同時実行アプリケーションを開発するためやすさを促進する命令型プログラミング モデルを提供する PPL について説明します。  
  
## <a name="reference"></a>参照  
 [concurrent_vector クラス](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [concurrent_queue クラス](../Topic/concurrent_queue%20Class.md)  
  
 [concurrent_unordered_map クラス](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [concurrent_unordered_multimap クラス](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [concurrent_unordered_set クラス](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [concurrent_unordered_multiset クラス](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [combinable クラス](../../parallel/concrt/reference/combinable-class.md)
