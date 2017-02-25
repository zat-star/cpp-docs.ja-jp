---
title: "hash_multimap (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/hash_map> ヘッダー [STL/CLR]"
  - "<hash_map> ヘッダー [STL/CLR]"
  - "hash_multimap クラス [STL/CLR]"
ms.assetid: cd78687b-8a05-48e0-9d22-8b8194ae3b0b
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# hash_multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロールと双方向アクセスできる要素の可変長シーケンスを記述します。  ハッシュ テーブル、ノードの双方向リンク リストを格納する各テーブル エントリと 1 種類の要素を格納できる各ノードとして要素のシーケンスを管理するために `hash_multimap` コンテナーを使用します。  要素がシーケンスを、乗車に移動マップされたな値を使用するためのキーで構成されています。  
  
 以下の説明では `GValue` は同じです:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 それぞれの文字について以下に説明します。  
  
 `GKey` は `Key` な型が `Key^`場合、後者は ref 型である同じになりますが、  
  
 `GMapped` は `Mapped` な型が `Mapped^`場合、後者は ref 型である同じになりますが、  
  
## 構文  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_multimap  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
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
|[hash\_multimap::const\_iterator](../dotnet/hash-multimap-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[hash\_multimap::const\_reference](../dotnet/hash-multimap-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[hash\_multimap::const\_reverse\_iterator](../Topic/hash_multimap::const_reverse_iterator%20\(STL-CLR\).md)|被制御シーケンスの定数反転反復子の型です。|  
|[hash\_multimap::difference\_type](../dotnet/hash-multimap-difference-type-stl-clr.md)|2 個の要素間の a \(場合に署名する\) 間隔の種類。|  
|[hash\_multimap::generic\_container](../dotnet/hash-multimap-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの種類。|  
|[hash\_multimap::generic\_iterator](../dotnet/hash-multimap-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[hash\_multimap::generic\_reverse\_iterator](../dotnet/hash-multimap-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[hash\_multimap::generic\_value](../dotnet/hash-multimap-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[hash\_multimap::hasher](../dotnet/hash-multimap-hasher-stl-clr.md)|キーのハッシュのデリゲート。|  
|[hash\_multimap::iterator](../dotnet/hash-multimap-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[hash\_multimap::key\_compare](../dotnet/hash-multimap-key-compare-stl-clr.md)|2 種類のキーの順序のデリゲート。|  
|[hash\_multimap::key\_type](../dotnet/hash-multimap-key-type-stl-clr.md)|順序付けキーの型です。|  
|[hash\_multimap::mapped\_type](../Topic/hash_multimap::mapped_type%20\(STL-CLR\).md)|マップされたな値の型は、各キーに関連付けられています。|  
|[hash\_multimap::reference](../dotnet/hash-multimap-reference-stl-clr.md)|要素への参照の型です。|  
|[hash\_multimap::reverse\_iterator](../dotnet/hash-multimap-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[hash\_multimap::size\_type](../dotnet/hash-multimap-size-type-stl-clr.md)|2 個の要素間の a \(負\) 間隔の種類。|  
|[hash\_multimap::value\_compare](../dotnet/hash-multimap-value-compare-stl-clr.md)|2 要素の値の順序のデリゲート。|  
|[hash\_multimap::value\_type](../dotnet/hash-multimap-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[hash\_multimap::begin](../dotnet/hash-multimap-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[hash\_multimap::bucket\_count](../dotnet/hash-multimap-bucket-count-stl-clr.md)|バケット数をカウントします。|  
|[hash\_multimap::clear](../dotnet/hash-multimap-clear-stl-clr.md)|すべての要素を削除します。|  
|[hash\_multimap::count](../dotnet/hash-multimap-count-stl-clr.md)|指定したキーに一致する要素数をカウントします。|  
|[hash\_multimap::empty](../dotnet/hash-multimap-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[hash\_multimap::equal\_range](../dotnet/hash-multimap-equal-range-stl-clr.md)|指定したキーに一致する範囲を検索します。|  
|[hash\_multimap::erase](../dotnet/hash-multimap-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[hash\_multimap::find](../dotnet/hash-multimap-find-stl-clr.md)|指定したキーに一致する要素を検索します。|  
|[hash\_multimap::hash\_delegate](../dotnet/hash-multimap-hash-delegate-stl-clr.md)|キーのハッシュのデリゲートをコピーします。|  
|[hash\_multimap::hash\_multimap](../dotnet/hash-multimap-hash-multimap-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[hash\_multimap::insert](../dotnet/hash-multimap-insert-stl-clr.md)|要素を追加します。|  
|[hash\_multimap::key\_comp](../dotnet/hash-multimap-key-comp-stl-clr.md)|2 種類のキーの順序のデリゲートをコピーします。|  
|[hash\_multimap::load\_factor](../dotnet/hash-multimap-load-factor-stl-clr.md)|バケットごとの平均要素数をカウントします。|  
|[hash\_multimap::lower\_bound](../Topic/hash_multimap::lower_bound%20\(STL-CLR\).md)|指定したキーに一致する範囲の先頭を検索します。|  
|[hash\_multimap::make\_value](../dotnet/hash-multimap-make-value-stl-clr.md)|値オブジェクトを構築します。|  
|[hash\_multimap::max\_load\_factor](../Topic/hash_multimap::max_load_factor%20\(STL-CLR\).md)|バケットあたりの最大要素数を取得または設定します。|  
|[hash\_multimap::rbegin](../dotnet/hash-multimap-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[hash\_multimap::rehash](../dotnet/hash-multimap-rehash-stl-clr.md)|ハッシュ テーブルを再構築します。|  
|[hash\_multimap::rend](../dotnet/hash-multimap-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[hash\_multimap::size](../dotnet/hash-multimap-size-stl-clr.md)|要素の数をカウントします。|  
|[hash\_multimap::swap](../dotnet/hash-multimap-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[hash\_multimap::to\_array](../dotnet/hash-multimap-to-array-stl-clr.md)|新しい配列に被制御シーケンスをコピーします。|  
|[hash\_multimap::upper\_bound](../Topic/hash_multimap::upper_bound%20\(STL-CLR\).md)|指定したキーに一致する範囲の末尾を検索します。|  
|[hash\_multimap::value\_comp](../dotnet/hash-multimap-value-comp-stl-clr.md)|2 要素の値の順序のデリゲートをコピーします。|  
  
|演算子|説明|  
|---------|--------|  
|[hash\_multimap::operator\=](../dotnet/hash-multimap-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
  
## インターフェイス  
  
|インターフェイス|説明|  
|--------------|--------|  
|<xref:System.ICloneable>|オブジェクトを複製します。|  
|<xref:System.Collections.IEnumerable>|要素によるシーケンス。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|指定された要素を通じてシーケンス。|  
|<xref:System.Collections.Generic.ICollection%601>|指定された要素のグループを保持します。|  
|IHashKey\<の値\>|一般的なコンテナーを保持します。|  
  
## 解説  
 オブジェクトは、双方向のリンク リストの個々のノードとして被制御シーケンスに対するストレージの割り当て。  アクセスを高速化するには、オブジェクトのリスト \(ハッシュ テーブル\) に効果的にサブリストのシーケンスとしてリスト全体、またはバケットを管理するポインターの可変長の配列を保持します。  これにより、ノード間のリンクの変更に並べるさせてバケットに他方に 1 ノードの内容をコピーして要素を、挿入されません。  これはブロックの最初の要素を除いた要素を自由に挿入および削除できることを意味します。  
  
 オブジェクトの型は [hash\_set::key\_compare](../Topic/hash_set::key_compare%20\(STL-CLR\).md)に保存されたデリゲート オブジェクトを呼び出して制御する各バケットを並べ替えます。  hash\_set を構築するときに格納されたデリゲート オブジェクトを指定する; デリゲート オブジェクトを指定しない場合、既定は比較 `operator<=(key_type, key_type)`です。  
  
 メンバー関数 [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()`を呼び出して格納されたデリゲート オブジェクトにアクセスします。  このようなデリゲート オブジェクトは型 [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md)のキーの間に並べる等価を定義する必要があります。  このいずれかの 2 種類のキー `X` と `Y`のメジャー、:  
  
 `key_comp()(X, Y)` は 呼び出しごとに同じブール型の結果を返します。  
  
 `key_comp()(X, Y) && key_comp()(Y, X)` が TRUE の場合、同じ大小関係があると `Y` は `X` と呼ばれます。  
  
 `operator<=(key_type, key_type)`、`operator>=(key_type, key_type)` または `operator==(key_type, key_type)` のように動作する順序規則が eqivalent 順序を定義します。  
  
 キーに等価の順序と同じ整数値にハッシュし、要素 \(\) バケット内に並んでいることだけコンテナーを使用することに注意してください。  [hash\_map](../dotnet/hash-map-stl-clr.md)テンプレート クラスとは異なり、テンプレート クラス `hash_multimap` オブジェクトはすべての要素のキーが一意である必要はありません。\(複数のキーは同じ大小関係を持つことができます。  
  
 オブジェクトは、バケットの型 [hash\_set::hasher](../Topic/hash_set::hasher%20\(STL-CLR\).md)かの格納されたデリゲート オブジェクトを呼び出すと、特定の順序付けキーを含める必要があるかを判断します。  キー値に依存する整数値を取得するに [hash\_set::hash\_delegate](../Topic/hash_set::hash_delegate%20\(STL-CLR\).md)`()` メンバー関数を呼び出すことで、保存されたオブジェクトにアクセスします。  hash\_set を構築するときに格納されたデリゲート オブジェクトを指定する; デリゲート オブジェクトを指定しない場合、既定は関数 `System::Object::hash_value(key_type)`です。  このキー `X` と `Y`のメジャー、:  
  
 `hash_delegate()(X)` は 呼び出しごとに同じ結果の整数値を返します。  
  
 `X` と `Y` 同じ大小関係がある場合、`hash_delegate()(X)` は `hash_delegate()(Y)`と同じ結果の整数値を返します。  
  
 各要素は、別のキーとマップされたな値が含まれます。  このシーケンスは、\(定数時間\) 要素の数とは無関係に行われる一連のアクションを使用して、任意の要素を検索、挿入、および削除を有効にすることで表されます。。少なくとも場合に最適です。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 ハッシュ値は、ですが、配布、ハッシュ テーブルが減少します。  極端。同じ値を常に返すハッシュ関数の場合。表示、挿入、削除、シーケンス \(線形時間\) 内の要素数に比例します。  コンテナーは、適切なハッシュ関数、平均のバケットのサイズ、およびハッシュ テーブルのサイズ \(バケット数\) を選択するようにコミットしてこれらの選択の一部またはすべてをオーバーライドできます。  たとえば、関数 [hash\_set::max\_load\_factor](../Topic/hash_set::max_load_factor%20\(STL-CLR\).md) と [hash\_set::rehash](../Topic/hash_set::rehash%20\(STL-CLR\).md)を参照してください。  
  
 hash\_multimap はメジャーは、被制御シーケンスの要素を指定する反復子を持つ隣接する要素にステップ インできる双方向の反復子がサポートされています。  特別なヘッド ノードは [hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)`()`が返す反復子に対応します。  存在する場合、被制御シーケンスの最後の要素にアクセスするためにこの反復子をデクリメントすることができます。  ヘッド ノードに到達するために hash\_multimap の反復子をインクリメントすることができます `end()`と等号を比較します。  ただし、`end()`が返す反復子を逆参照できません。  
  
 直接数値位置が、hash\_multimap の要素を参照できないことに注意してください。。これはランダム アクセス反復子を必要とします。  
  
 hash\_multimap の反復子は、関連するコンテナーにハンドルを格納する関連付けられた hash\_multimap ノードへのハンドルを格納します。  関連するコンテナー オブジェクトでのみ反復子を使用できます。  hash\_multimap の反復子は、関連する hash\_multimap ノードが hash\_multimap に関連付けられている限り有効です。  また、有効な反復子は dereferencable です。指定した要素の値にアクセスするか、または変更するために使用できます。。これは `end()`と等しくない場合。  
  
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