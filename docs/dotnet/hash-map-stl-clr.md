---
title: "hash_map (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/hash_map> ヘッダー [STL/CLR]"
  - "<hash_map> ヘッダー [STL/CLR]"
  - "hash_map クラス [STL/CLR]"
ms.assetid: c3cfc69b-04c6-42ae-a30e-0eda953fe883
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# hash_map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロールと双方向アクセスできる要素の可変長シーケンスを記述します。  ハッシュ テーブル、ノードの双方向リンク リストを格納する各テーブル エントリと 1 種類の要素を格納できる各ノードとして要素のシーケンスを管理するために `hash_map` コンテナーを使用します。  要素がシーケンスを、乗車に移動マップされたな値を使用するためのキーで構成されています。  
  
 以下の説明では `GValue` は同じです:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 それぞれの文字について以下に説明します。  
  
 `GKey` は `Key` な型が `Key^`場合、後者は ref 型である同じになりますが、  
  
 `GMapped` は `Mapped` な型が `Mapped^`場合、後者は ref 型である同じになりますが、  
  
## 構文  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### パラメーター  
 キー  
 被制御シーケンス内の要素のキー コンポーネントの型。  
  
 マップ  
 被制御シーケンスの要素の追加コンポーネントの型。  
  
## メンバー  
  
|型定義|説明|  
|---------|--------|  
|[hash\_map::const\_iterator](../dotnet/hash-map-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[hash\_map::const\_reference](../dotnet/hash-map-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[hash\_map::const\_reverse\_iterator](../dotnet/hash-map-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[hash\_map::difference\_type](../dotnet/hash-map-difference-type-stl-clr.md)|2 個の要素間の a \(場合に署名する\) 間隔の種類。|  
|[hash\_map::generic\_container](../dotnet/hash-map-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの種類。|  
|[hash\_map::generic\_iterator](../dotnet/hash-map-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[hash\_map::generic\_reverse\_iterator](../dotnet/hash-map-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[hash\_map::generic\_value](../dotnet/hash-map-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[hash\_map::hasher](../dotnet/hash-map-hasher-stl-clr.md)|キーのハッシュのデリゲート。|  
|[hash\_map::iterator](../dotnet/hash-map-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[hash\_map::key\_compare](../Topic/hash_map::key_compare%20\(STL-CLR\).md)|2 種類のキーの順序のデリゲート。|  
|[hash\_map::key\_type](../Topic/hash_map::key_type%20\(STL-CLR\).md)|順序付けキーの型です。|  
|[hash\_map::mapped\_type](../Topic/hash_map::mapped_type%20\(STL-CLR\).md)|マップされたな値の型は、各キーに関連付けられています。|  
|[hash\_map::reference](../dotnet/hash-map-reference-stl-clr.md)|要素への参照の型です。|  
|[hash\_map::reverse\_iterator](../dotnet/hash-map-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[hash\_map::size\_type](../Topic/hash_map::size_type%20\(STL-CLR\).md)|2 個の要素間の a \(負\) 間隔の種類。|  
|[hash\_map::value\_compare](../dotnet/hash-map-value-compare-stl-clr.md)|2 要素の値の順序のデリゲート。|  
|[hash\_map::value\_type](../dotnet/hash-map-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[hash\_map::begin](../dotnet/hash-map-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[hash\_map::bucket\_count](../dotnet/hash-map-bucket-count-stl-clr.md)|バケット数をカウントします。|  
|[hash\_map::clear](../Topic/hash_map::clear%20\(STL-CLR\).md)|すべての要素を削除します。|  
|[hash\_map::count](../dotnet/hash-map-count-stl-clr.md)|指定したキーに一致する要素数をカウントします。|  
|[hash\_map::empty](../dotnet/hash-map-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[hash\_map::end](../dotnet/hash-map-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[hash\_map::equal\_range](../dotnet/hash-map-equal-range-stl-clr.md)|指定したキーに一致する範囲を検索します。|  
|[hash\_map::erase](../dotnet/hash-map-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[hash\_map::find](../dotnet/hash-map-find-stl-clr.md)|指定したキーに一致する要素を検索します。|  
|[hash\_map::hash\_delegate](../dotnet/hash-map-hash-delegate-stl-clr.md)|キーのハッシュのデリゲートをコピーします。|  
|[hash\_map::hash\_map](../dotnet/hash-map-hash-map-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[hash\_map::insert](../Topic/hash_map::insert%20\(STL-CLR\).md)|要素を追加します。|  
|[hash\_map::key\_comp](../dotnet/hash-map-key-comp-stl-clr.md)|2 種類のキーの順序のデリゲートをコピーします。|  
|[hash\_map::load\_factor](../dotnet/hash-map-load-factor-stl-clr.md)|バケットごとの平均要素数をカウントします。|  
|[hash\_map::lower\_bound](../dotnet/hash-map-lower-bound-stl-clr.md)|指定したキーに一致する範囲の先頭を検索します。|  
|[hash\_map::make\_value](../dotnet/hash-map-make-value-stl-clr.md)|値オブジェクトを構築します。|  
|[hash\_map::max\_load\_factor](../dotnet/hash-map-max-load-factor-stl-clr.md)|バケットあたりの最大要素数を取得または設定します。|  
|[hash\_map::rbegin](../dotnet/hash-map-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[hash\_map::rehash](../dotnet/hash-map-rehash-stl-clr.md)|ハッシュ テーブルを再構築します。|  
|[hash\_map::rend](../Topic/hash_map::rend%20\(STL-CLR\).md)|反転被制御シーケンスの末尾を指定します。|  
|[hash\_map::size](../dotnet/hash-map-size-stl-clr.md)|要素の数をカウントします。|  
|[hash\_map::swap](../dotnet/hash-map-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[hash\_map::to\_array](../dotnet/hash-map-to-array-stl-clr.md)|新しい配列に被制御シーケンスをコピーします。|  
|[hash\_map::upper\_bound](../dotnet/hash-map-upper-bound-stl-clr.md)|指定したキーに一致する範囲の末尾を検索します。|  
|[hash\_map::value\_comp](../dotnet/hash-map-value-comp-stl-clr.md)|2 要素の値の順序のデリゲートをコピーします。|  
  
|演算子|説明|  
|---------|--------|  
|[hash\_map::operator\=](../dotnet/hash-map-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[hash\_map::operator](../dotnet/hash-map-operator-stl-clr.md)|関連するマップされたな値にキーを割り当てます。|  
  
## インターフェイス  
  
|インターフェイス|説明|  
|--------------|--------|  
|<xref:System.ICloneable>|オブジェクトを複製します。|  
|<xref:System.Collections.IEnumerable>|要素によるシーケンス。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|指定された要素を通じてシーケンス。|  
|<xref:System.Collections.Generic.ICollection%601>|指定された要素のグループを保持します。|  
|<xref:System.Collections.Generic.IDictionary%602>|{}値、キー ペアのグループを保持します。|  
|IHashKey\<の値\>|一般的なコンテナーを保持します。|  
  
## 解説  
 オブジェクトは、双方向のリンク リストの個々のノードとして被制御シーケンスに対するストレージの割り当て。  アクセスを高速化するには、オブジェクトのリスト \(ハッシュ テーブル\) に効果的にサブリストのシーケンスとしてリスト全体、またはバケットを管理するポインターの可変長の配列を保持します。  これにより、ノード間のリンクの変更に並べるさせてバケットに他方に 1 ノードの内容をコピーして要素を、挿入されません。  これはブロックの最初の要素を除いた要素を自由に挿入および削除できることを意味します。  
  
 オブジェクトの型は [hash\_set::key\_compare](../Topic/hash_set::key_compare%20\(STL-CLR\).md)に保存されたデリゲート オブジェクトを呼び出して制御する各バケットを並べ替えます。  hash\_set を構築するときに格納されたデリゲート オブジェクトを指定する; デリゲート オブジェクトを指定しない場合、既定は比較 `operator<=(key_type, key_type)`です。  
  
 メンバー関数 [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()`を呼び出して格納されたデリゲート オブジェクトにアクセスします。  このようなデリゲート オブジェクトは型 [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md)のキーの間に並べる等価を定義する必要があります。  このいずれかの 2 種類のキー `X` と `Y`のメジャー、:  
  
 `key_comp()(X, Y)` は 呼び出しごとに同じブール型の結果を返します。  
  
 `key_comp()(X, Y) && key_comp()(Y, X)` が TRUE の場合、同じ大小関係があると `Y` は `X` と呼ばれます。  
  
 `operator<=(key_type, key_type)`、`operator>=(key_type, key_type)` または `operator==(key_type, key_type)` のように動作する順序規則が eqivalent 順序を定義します。  
  
 キーに等価の順序と同じ整数値にハッシュし、要素 \(\) バケット内に並んでいることだけコンテナーを使用することに注意してください。  [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)テンプレート クラスとは異なり、テンプレート クラス `hash_map` オブジェクトはすべての要素のキーが一意であることを確認します。\(2 番目のキーに同じ大小関係はありません\)。  
  
 オブジェクトは、バケットの型 [hash\_set::hasher](../Topic/hash_set::hasher%20\(STL-CLR\).md)かの格納されたデリゲート オブジェクトを呼び出すと、特定の順序付けキーを含める必要があるかを判断します。  キー値に依存する整数値を取得するに [hash\_set::hash\_delegate](../Topic/hash_set::hash_delegate%20\(STL-CLR\).md)`()` メンバー関数を呼び出すことで、保存されたオブジェクトにアクセスします。  hash\_set を構築するときに格納されたデリゲート オブジェクトを指定する; デリゲート オブジェクトを指定しない場合、既定は関数 `System::Object::hash_value(key_type)`です。  このキー `X` と `Y`のメジャー、:  
  
 `hash_delegate()(X)` は 呼び出しごとに同じ結果の整数値を返します。  
  
 `X` と `Y` 同じ大小関係がある場合、`hash_delegate()(X)` は `hash_delegate()(Y)`と同じ結果の整数値を返します。  
  
 各要素は、別のキーとマップされたな値が含まれます。  このシーケンスは、\(定数時間\) 要素の数とは無関係に行われる一連のアクションを使用して、任意の要素を検索、挿入、および削除を有効にすることで表されます。。少なくとも場合に最適です。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 ハッシュ値は、ですが、配布、ハッシュ テーブルが減少します。  極端。同じ値を常に返すハッシュ関数の場合。表示、挿入、削除、シーケンス \(線形時間\) 内の要素数に比例します。  コンテナーは、適切なハッシュ関数、平均のバケットのサイズ、およびハッシュ テーブルのサイズ \(バケット数\) を選択するようにコミットしてこれらの選択の一部またはすべてをオーバーライドできます。  たとえば、関数 [hash\_set::max\_load\_factor](../Topic/hash_set::max_load_factor%20\(STL-CLR\).md) と [hash\_set::rehash](../Topic/hash_set::rehash%20\(STL-CLR\).md)を参照してください。  
  
 hash\_map はメジャーは、被制御シーケンスの要素を指定する反復子を持つ隣接する要素にステップ インできる双方向の反復子がサポートされています。  特別なヘッド ノードは [hash\_map::end](../dotnet/hash-map-end-stl-clr.md)`()`が返す反復子に対応します。  存在する場合、被制御シーケンスの最後の要素にアクセスするためにこの反復子をデクリメントすることができます。  ヘッド ノードに到達するために hash\_map の反復子をインクリメントすることができます `end()`と等号を比較します。  ただし、`end()`が返す反復子を逆参照できません。  
  
 直接数値位置が、hash\_map の要素を参照できないことに注意してください。。これはランダム アクセス反復子を必要とします。  
  
 hash\_map の反復子は、関連するコンテナーにハンドルを格納する関連付けられた hash\_map ノードへのハンドルを格納します。  関連するコンテナー オブジェクトでのみ反復子を使用できます。  hash\_map の反復子は、関連する hash\_map ノードが hash\_map に関連付けられている限り有効です。  また、有効な反復子は dereferencable です。指定した要素の値にアクセスするか、または変更するために使用できます。。これは `end()`と等しくない場合。  
  
 要素に設定するか、削除して、格納されている値のデストラクターを呼び出します。  コンテナーが破棄されると、すべての要素を消去します。  したがって、要素の型が ref クラスにあるコンテナー要素がコンテナーを重視されることを確認します。  ただし、Handles のコンテナーが `not` の要素を破棄されます。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_map\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [マップ](../dotnet/map-stl-clr.md)   
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [設定](../dotnet/set-stl-clr.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)