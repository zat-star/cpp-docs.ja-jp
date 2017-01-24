---
title: "hash_multiset (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/hash_set> ヘッダー [STL/CLR]"
  - "<hash_set> ヘッダー [STL/CLR]"
  - "hash_multiset クラス [STL/CLR]"
ms.assetid: 8462bd21-6829-4dd3-ac81-c42d6fdf92f0
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロールと双方向アクセスできる要素の可変長シーケンスを記述します。  ハッシュ テーブル、ノードの双方向リンク リストを格納する各テーブル エントリと 1 種類の要素を格納できる各ノードとして要素のシーケンスを管理するために `hash_multiset` コンテナーを使用します。  各要素の値は、シーケンスの順序を指定するためのキーとして使用されます。  
  
 以下の説明では `GValue` は `GKey`な型が `Key^`場合、後者は ref 型である `Key` と同じの場合と同じです。  
  
## 構文  
  
```  
template<typename Key>  
    ref class hash_multiset  
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
  
## メンバー  
  
|型定義|説明|  
|---------|--------|  
|[hash\_multiset::const\_iterator](../dotnet/hash-multiset-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[hash\_multiset::const\_reference](../dotnet/hash-multiset-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[hash\_multiset::const\_reverse\_iterator](../dotnet/hash-multiset-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[hash\_multiset::difference\_type](../dotnet/hash-multiset-difference-type-stl-clr.md)|2 個の要素間の a \(場合に署名する\) 間隔の種類。|  
|[hash\_multiset::generic\_container](../dotnet/hash-multiset-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの種類。|  
|[hash\_multiset::generic\_iterator](../dotnet/hash-multiset-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[hash\_multiset::generic\_reverse\_iterator](../dotnet/hash-multiset-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[hash\_multiset::generic\_value](../dotnet/hash-multiset-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[hash\_multiset::hasher](../dotnet/hash-multiset-hasher-stl-clr.md)|キーのハッシュのデリゲート。|  
|[hash\_multiset::iterator](../dotnet/hash-multiset-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[hash\_multiset::key\_compare](../dotnet/hash-multiset-key-compare-stl-clr.md)|2 種類のキーの順序のデリゲート。|  
|[hash\_multiset::key\_type](../dotnet/hash-multiset-key-type-stl-clr.md)|順序付けキーの型です。|  
|[hash\_multiset::reference](../dotnet/hash-multiset-reference-stl-clr.md)|要素への参照の型です。|  
|[hash\_multiset::reverse\_iterator](../dotnet/hash-multiset-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[hash\_multiset::size\_type](../dotnet/hash-multiset-size-type-stl-clr.md)|2 個の要素間の a \(負\) 間隔の種類。|  
|[hash\_multiset::value\_compare](../dotnet/hash-multiset-value-compare-stl-clr.md)|2 要素の値の順序のデリゲート。|  
|[hash\_multiset::value\_type](../dotnet/hash-multiset-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[hash\_multiset::begin](../dotnet/hash-multiset-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[hash\_multiset::bucket\_count](../dotnet/hash-multiset-bucket-count-stl-clr.md)|バケット数をカウントします。|  
|[hash\_multiset::clear](../dotnet/hash-multiset-clear-stl-clr.md)|すべての要素を削除します。|  
|[hash\_multiset::count](../dotnet/hash-multiset-count-stl-clr.md)|指定したキーに一致する要素数をカウントします。|  
|[hash\_multiset::empty](../dotnet/hash-multiset-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[hash\_multiset::equal\_range](../Topic/hash_multiset::equal_range%20\(STL-CLR\).md)|指定したキーに一致する範囲を検索します。|  
|[hash\_multiset::erase](../dotnet/hash-multiset-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[hash\_multiset::find](../dotnet/hash-multiset-find-stl-clr.md)|指定したキーに一致する要素を検索します。|  
|[hash\_multiset::hash\_delegate](../dotnet/hash-multiset-hash-delegate-stl-clr.md)|キーのハッシュのデリゲートをコピーします。|  
|[hash\_multiset::hash\_multiset](../dotnet/hash-multiset-hash-multiset-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[hash\_multiset::insert](../Topic/hash_multiset::insert%20\(STL-CLR\).md)|要素を追加します。|  
|[hash\_multiset::key\_comp](../dotnet/hash-multiset-key-comp-stl-clr.md)|2 種類のキーの順序のデリゲートをコピーします。|  
|[hash\_multiset::load\_factor](../Topic/hash_multiset::load_factor%20\(STL-CLR\).md)|バケットごとの平均要素数をカウントします。|  
|[hash\_multiset::lower\_bound](../Topic/hash_multiset::lower_bound%20\(STL-CLR\).md)|指定したキーに一致する範囲の先頭を検索します。|  
|[hash\_multiset::make\_value](../dotnet/hash-multiset-make-value-stl-clr.md)|値オブジェクトを構築します。|  
|[hash\_multiset::max\_load\_factor](../dotnet/hash-multiset-max-load-factor-stl-clr.md)|バケットあたりの最大要素数を取得または設定します。|  
|[hash\_multiset::rbegin](../Topic/hash_multiset::rbegin%20\(STL-CLR\).md)|反転被制御シーケンスの先頭を指定します。|  
|[hash\_multiset::rehash](../Topic/hash_multiset::rehash%20\(STL-CLR\).md)|ハッシュ テーブルを再構築します。|  
|[hash\_multiset::rend](../dotnet/hash-multiset-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[hash\_multiset::size](../Topic/hash_multiset::size%20\(STL-CLR\).md)|要素の数をカウントします。|  
|[hash\_multiset::swap](../dotnet/hash-multiset-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[hash\_multiset::to\_array](../dotnet/hash-multiset-to-array-stl-clr.md)|新しい配列に被制御シーケンスをコピーします。|  
|[hash\_multiset::upper\_bound](../dotnet/hash-multiset-upper-bound-stl-clr.md)|指定したキーに一致する範囲の末尾を検索します。|  
|[hash\_multiset::value\_comp](../dotnet/hash-multiset-value-comp-stl-clr.md)|2 要素の値の順序のデリゲートをコピーします。|  
  
|演算子|説明|  
|---------|--------|  
|[hash\_multiset::operator\=](../dotnet/hash-multiset-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
  
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
  
 キーに等価の順序と同じ整数値にハッシュし、要素 \(\) バケット内に並んでいることだけコンテナーを使用することに注意してください。  [hash\_set](../dotnet/hash-set-stl-clr.md)テンプレート クラスとは異なり、テンプレート クラス `hash_multiset` オブジェクトはすべての要素のキーが一意である必要はありません。\(複数のキーは同じ大小関係を持つことができます。  
  
 オブジェクトは、バケットの型 [hash\_set::hasher](../Topic/hash_set::hasher%20\(STL-CLR\).md)かの格納されたデリゲート オブジェクトを呼び出すと、特定の順序付けキーを含める必要があるかを判断します。  キー値に依存する整数値を取得するに [hash\_set::hash\_delegate](../Topic/hash_set::hash_delegate%20\(STL-CLR\).md)`()` メンバー関数を呼び出すことで、保存されたオブジェクトにアクセスします。  hash\_set を構築するときに格納されたデリゲート オブジェクトを指定する; デリゲート オブジェクトを指定しない場合、既定は関数 `System::Object::hash_value(key_type)`です。  このキー `X` と `Y`のメジャー、:  
  
 `hash_delegate()(X)` は 呼び出しごとに同じ結果の整数値を返します。  
  
 `X` と `Y` 同じ大小関係がある場合、`hash_delegate()(X)` は `hash_delegate()(Y)`と同じ結果の整数値を返します。  
  
 各要素はキーと値の両方として機能します。  このシーケンスは、\(定数時間\) 要素の数とは無関係に行われる一連のアクションを使用して、任意の要素を検索、挿入、および削除を有効にすることで表されます。。少なくとも場合に最適です。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 ハッシュ値は、ですが、配布、ハッシュ テーブルが減少します。  極端。同じ値を常に返すハッシュ関数の場合。表示、挿入、削除、シーケンス \(線形時間\) 内の要素数に比例します。  コンテナーは、適切なハッシュ関数、平均のバケットのサイズ、およびハッシュ テーブルのサイズ \(バケット数\) を選択するようにコミットしてこれらの選択の一部またはすべてをオーバーライドできます。  たとえば、関数 [hash\_set::max\_load\_factor](../Topic/hash_set::max_load_factor%20\(STL-CLR\).md) と [hash\_set::rehash](../Topic/hash_set::rehash%20\(STL-CLR\).md)を参照してください。  
  
 hash\_multiset はメジャーは、被制御シーケンスの要素を指定する反復子を持つ隣接する要素にステップ インできる双方向の反復子がサポートされています。  特別なヘッド ノードは [hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`()`が返す反復子に対応します。  存在する場合、被制御シーケンスの最後の要素にアクセスするためにこの反復子をデクリメントすることができます。  ヘッド ノードに到達するために hash\_multiset の反復子をインクリメントすることができます `end()`と等号を比較します。  ただし、`end()`が返す反復子を逆参照できません。  
  
 直接数値位置が、hash\_multiset の要素を参照できないことに注意してください。。これはランダム アクセス反復子を必要とします。  
  
 hash\_multiset の反復子は、関連するコンテナーにハンドルを格納する関連付けられた hash\_multiset ノードへのハンドルを格納します。  関連するコンテナー オブジェクトでのみ反復子を使用できます。  hash\_multiset の反復子は、関連する hash\_multiset ノードが hash\_multiset に関連付けられている限り有効です。  また、有効な反復子は dereferencable です。指定した要素の値にアクセスするか、または変更するために使用できます。。これは `end()`と等しくない場合。  
  
 要素に設定するか、削除して、格納されている値のデストラクターを呼び出します。  コンテナーが破棄されると、すべての要素を消去します。  したがって、要素の型が ref クラスにあるコンテナー要素がコンテナーを重視されることを確認します。  ただし、Handles のコンテナーが `not` の要素を破棄されます。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [マップ](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [設定](../dotnet/set-stl-clr.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)