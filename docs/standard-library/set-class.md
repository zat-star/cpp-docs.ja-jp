---
title: "set クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::set"
  - "set"
  - "set/std::set"
  - "std.set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set クラス"
ms.assetid: 8991f9aa-5509-4440-adc1-371512d32018
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# set クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL コンテナー クラスの set は、コレクションのデータを格納および取得するために使用されます。コレクションに含まれる要素の値は一意であり、データが自動的に順序付けられるときにキー値として使用されます。  set 内の要素の値は直接変更できません。  代わりに、以前の値を削除し、新しい値の要素を挿入する必要があります。  
  
## 構文  
  
```  
template <  
    class Key,   
    class Traits=less<Key>,   
    class Allocator=allocator<Key>   
>  
class set  
```  
  
#### パラメーター  
 `Key`  
 set に格納される要素のデータ型。  
  
 `Traits`  
 2 つの要素の値を並べ替えキーとして比較して、set 内の要素の相対順序を決定できる関数オブジェクトを提供する型。  この引数は省略可能であり、既定値は二項述語 **less***\<Key\>* です。  
  
 C\+\+ 14 では、型パラメーターを使用せずに `std::less<>` 述語または `std::greater<>` 述語を指定することで、異種ルックアップを有効にすることができます。  詳細については、「[連想コンテナーの異種ルックアップ](../standard-library/stl-containers.md#sequence_containers)」を参照してください。  
  
 `Allocator`  
 メモリの set の割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  この引数は省略可能であり、既定値は **allocator***\<Key\>* です。  
  
## 解説  
 STL の set の特徴は次のとおりです。  
  
-   hash\_map は連想コンテナーであり、関連付けられたキー値に基づいて要素の値を効率的に取得できるようにする可変サイズのコンテナーとして機能します。  さらに、単純な連想コンテナーです。これは、要素値がキー値であるためです。  
  
-   反転することができます。これは、hash\_map には、要素にアクセスするための双方向反復子が用意されているためです。  
  
-   並べ替えが実行されます。これは、指定した比較関数に従ってコンテナー内のキー値によって要素に順序が設定されるためです。  
  
-   一意のクラスです。これは、各要素が一意のキーを持つ必要があるためです。  set は、単純な連想コンテナーであるため、要素も一意です。  
  
 set はテンプレート クラスとしても表されます。これは、このクラスに用意されている機能が汎用的な機能であり、要素またはキーとして保持されているデータの特定の型に依存しないためです。  使用されているデータ型は、クラス テンプレートで比較関数やアロケーターと共にパラメーターとして指定されます。  
  
 一般的に、コンテナー型の選択は、アプリケーションにおいて必要な検索および挿入の種類に基づいている必要があります。  連想コンテナーは、検索、挿入、削除の各操作用に最適化されています。  これらの操作を明示的にサポートするメンバー関数は効率的であり、処理時間は平均的にコンテナー内にある要素の数の対数に比例します。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を具体的に指す反復子だけが無効化されます。  
  
 値とキーを関連付ける条件をアプリケーションが満たしている場合、set は最適な連想コンテナーとなっている必要があります。  set の要素は一意であり、独自の並べ替えキーとして機能します。  この種類の構造体のモデルは、単語が 1 回だけ出現する可能性がある単語の順序付きのリストです。  キーワードを複数設定できる場合は、multiset が適切なコンテナー構造体となります。  値が一意のキーワードのリストにアタッチされている必要がある場合、map がこのデータを格納するのに適切な構造体です。  キーが一意でない場合は、multimap が最適なコンテナーです。  
  
 set では、[key\_compare](../Topic/set::key_compare.md) 型の格納されている関数オブジェクトを呼び出すことによって、set が制御するシーケンスを並べ替えます。  格納されているこのオブジェクトは比較関数であり、メンバー関数 [key\_comp](../Topic/set::key_comp.md) を呼び出すことによってアクセスできます。  通常、要素は、この順序を確立するために小なり比較だけを実行できる必要があります。これにより、2 つの要素が指定されたときに、それらの要素が等しいか \(どちらか一方が小さくはない\)、または一方が他方より小さいかを判断できます。  この結果、等価でない複数の要素間で順序が付けられます。  テクニカル ノートでは、比較関数は、数学上の標準的な意味で厳密弱順序を発生させる二項述語であると示されています。  二項述語 *f*\(*x,y*\) は、2 つの引数オブジェクト \(*x* および *y*\) と戻り値 \(**true** または **false**\) を持つ関数オブジェクトです。  set に適用される順序付けは、二項述語が非再帰、反対称、推移的であり、等価性が推移的である \(2 つのオブジェクト *x* と *y*が、*f*\(*x,y*\) と *f*\(*y,x*\) の両方が false の場合に等価になるように定義されている\) 場合、厳密弱順序になります。  2 つのキーの等値に関する条件が等価性の条件よりも厳しく、優先される場合、順序付けは完全な順序付け \(すべての要素が相互の値に基づいて並べ替えられる\) となり、一致するそれぞれのキーを識別するのが難しくなります。  
  
 C\+\+ 14 では、型パラメーターを使用せずに `std::less<>` 述語または `std::greater<>` 述語を指定することで、異種ルックアップを有効にすることができます。  詳細については、「[連想コンテナーの異種ルックアップ](../standard-library/stl-containers.md#sequence_containers)」を参照してください。  
  
 set クラスに用意されている反復子は双方向反復子ですが、クラス メンバー関数 [insert](../Topic/set::insert.md) と [set](../Topic/set::set.md) には、弱い入力反復子をテンプレート パラメーターとして取得するバージョンがあります。この反復子の機能に関する要件は、双方向反復子のクラスで保証されている要件よりも低くなっています。  これらの反復子の機能に差異があるのは、反復子の概念が異なっているためです。  反復子の各概念には、反復子独自の一連の要件が含まれています。また、それらの要件を使用するアルゴリズムでは、反復子の種類ごとに指定されている要件に対して、前提を絞り込む必要があります。  たとえば、一部のオブジェクトを参照するために入力反復子が逆参照される可能性があることを前提とする場合があります。さらに、シーケンス内にある次の反復子に対して逆参照が増加する可能性があることを前提とする場合もあります。  このことは、最小限実施することですが、クラスのメンバー関数のコンテキストに含まれる反復子の範囲 \[`First`, `Last`\) について明確にすることも重要です。  
  
### コンストラクター  
  
|||  
|-|-|  
|[設定](../Topic/set::set.md)|空の set を構築するか、他の set の全体または一部のコピーである set を構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/set::allocator_type.md)|set オブジェクトの `allocator` クラスを表す型。|  
|[const\_iterator](../Topic/set::const_iterator.md)|set 内の `const` 要素を読み取ることができる双方向反復子を提供する型。|  
|[const\_pointer](../Topic/set::const_pointer.md)|set 内の `const` 要素へのポインターを提供する型。|  
|[const\_reference](../Topic/set::const_reference.md)|読み取りと `const` 操作の実行のために、set に格納された `const` 要素への参照を提供する型。|  
|[const\_reverse\_iterator](../Topic/set::const_reverse_iterator.md)|set 内の任意の `const` 要素を読み取ることができる双方向反復子を提供する型。|  
|[difference\_type](../Topic/set::difference_type.md)|set の要素の数を、反復子が指す要素の範囲に基づいて表すために使用できる符号付き整数型。|  
|[iterator](../Topic/set::iterator.md)|set 内の任意の要素の読み取りまたは変更ができる双方向反復子を提供する型。|  
|[key\_compare](../Topic/set::key_compare.md)|2 つの並べ替えキーを比較して、set 内の 2 つの要素の相対順序を決定できる関数オブジェクトを提供する型。|  
|[key\_type](../Topic/set::key_type.md)|この型は、並べ替えキーとしてキャパシティ内で set の要素として格納されるオブジェクトを表します。|  
|[ポインター](../Topic/set::pointer.md)|set 内の要素へのポインターを提供する型。|  
|[参照](../Topic/set::reference.md)|set に格納されている要素への参照を提供する型。|  
|[reverse\_iterator](../Topic/set::reverse_iterator.md)|反転された set 内の 1 つの要素の読み取りまたは変更ができる双方向反復子を提供する型。|  
|[size\_type](../Topic/set::size_type.md)|set 内の要素の数を表すことができる符号なし整数型。|  
|[value\_compare](../Topic/set::value_compare.md)|2 つの要素を比較して、set 内の要素の相対順序を決定できる関数オブジェクトを提供する型。|  
|[value\_type](../Topic/set::value_type.md)|この型は、値としてキャパシティ内で set の要素として格納されるオブジェクトを表します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[begin](../Topic/set::begin.md)|set 内の最初の要素を指す定数反復子を返します。|  
|[cbegin](../Topic/set::cbegin.md)|set 内の最初の要素を指す定数反復子を返します。|  
|[cend](../Topic/set::cend.md)|set 内の最後の要素の次の位置を指す定数反復子を返します。|  
|[クリア](../Topic/set::clear.md)|set のすべての要素を消去します。|  
|[count](../Topic/set::count.md)|パラメーター指定したキーに一致するキーを持つ、set 内の要素の数を返します。|  
|[crbegin](../Topic/set::rbegin.md)|反転された set 内の最初の要素を指す定数反復子を返します。|  
|[crend](../Topic/set::rend.md)|反転された set 内の最後の要素の次の位置を指す定数反復子を返します。|  
|[emplace](../Topic/set::emplace.md)|インプレースで構築された要素を set に挿入します。|  
|[emplace\_hint](../Topic/set::emplace_hint.md)|インプレースで構築された要素を、配置ヒントと共に set に挿入します。|  
|[\(なし\)](../Topic/set::empty.md)|set が空かどうかをテストします。|  
|[End](../Topic/set::end.md)|set 内の最後の要素の次の位置を指す反復子を返します。|  
|[equal\_range](../Topic/set::equal_range.md)|指定したキーよりも大きいキーを持つ、set 内の最初の要素を指す反復子のペア、およびそのキー以上のキーを持つ、set 内の最初の要素を指す反復子のペアを返します。|  
|[erase](../Topic/set::erase.md)|セット内の要素または要素の範囲を指定した位置から削除するか、または指定したキーと一致する要素を削除します。|  
|[find](../Topic/set::find.md)|指定したキーと同じキーを持つ、set 内の要素の位置を指す反復子を返します。|  
|[get\_allocator](../Topic/set::get_allocator.md)|set の構築に使用される `allocator` オブジェクトのコピーを返します。|  
|[挿入](../Topic/set::insert.md)|set に要素または要素範囲を挿入します。|  
|[key\_comp](../Topic/set::key_comp.md)|set 内のキーを並べ替えるために使用される比較オブジェクトのコピーを取得します。|  
|[lower\_bound](../Topic/set::lower_bound.md)|指定したキー以上のキーを持つ、set 内の最初の要素を指す反復子を返します。|  
|[max\_size](../Topic/set::max_size.md)|set の最大長を返します。|  
|[rbegin](../Topic/set::rbegin.md)|反転された set 内の最初の要素を指す反復子を返します。|  
|[rend](../Topic/set::rend.md)|反転された set 内の最後の要素の次の位置を指す反復子を返します。|  
|[size](../Topic/set::size.md)|セット内の要素数を返します。|  
|[swap](../Topic/set::swap.md)|2 つの set の要素を交換します。|  
|[upper\_bound](../Topic/set::upper_bound.md)|指定したキーよりも大きいキーを持つ、set 内の最初の要素を指す反復子を返します。|  
|[value\_comp](../Topic/set::value_comp.md)|set 内の要素の値を並べ替えるために使用される比較オブジェクトのコピーを取得します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/set::operator=.md)|別の set のコピーで set の要素を置き換えます。|  
  
## 必要条件  
 **ヘッダー:** \<set\>  
  
 **名前空間:** std  
  
## 参照  
 [\<set\>](../standard-library/set.md)   
 [コンテナー](../Topic/Containers%20\(Modern%20C++\).md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)