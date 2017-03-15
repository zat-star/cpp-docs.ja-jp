---
title: "map (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/map> ヘッダー [STL/CLR]"
  - "<map> ヘッダー [STL/CLR]"
  - "map クラス [STL/CLR]"
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロールと双方向アクセスできる要素の可変長シーケンスを記述します。  a として要素のシーケンスを管理するには、コンテナー `map` \(ほとんど\) バランスをとりましたノードの順序が指定された、ツリー、保存の 1 要素を使用します。  要素がシーケンスを、乗車に移動マップされたな値を使用するためのキーで構成されています。  
  
 以下の説明では `GValue` は同じです:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 それぞれの文字について以下に説明します。  
  
 `GKey` は `Key` な型が `Key^`場合、後者は ref 型である同じになりますが、  
  
 `GMapped` は `Mapped` な型が `Mapped^`場合、後者は ref 型である同じになりますが、  
  
## 構文  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
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
|[map::const\_iterator](../dotnet/map-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[map::const\_reference](../dotnet/map-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[map::const\_reverse\_iterator](../dotnet/map-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[map::difference\_type](../dotnet/map-difference-type-stl-clr.md)|2 個の要素間の a \(場合に署名する\) 間隔の種類。|  
|[map::generic\_container](../Topic/map::generic_container%20\(STL-CLR\).md)|コンテナーのジェネリック インターフェイスの種類。|  
|[map::generic\_iterator](../dotnet/map-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[map::generic\_reverse\_iterator](../dotnet/map-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[map::generic\_value](../dotnet/map-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[map::iterator](../dotnet/map-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[map::key\_compare](../dotnet/map-key-compare-stl-clr.md)|2 種類のキーの順序のデリゲート。|  
|[map::key\_type](../dotnet/map-key-type-stl-clr.md)|順序付けキーの型です。|  
|[map::mapped\_type](../dotnet/map-mapped-type-stl-clr.md)|マップされたな値の型は、各キーに関連付けられています。|  
|[map::reference](../dotnet/map-reference-stl-clr.md)|要素への参照の型です。|  
|[map::reverse\_iterator](../dotnet/map-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[map::size\_type](../dotnet/map-size-type-stl-clr.md)|2 個の要素間の a \(負\) 間隔の種類。|  
|[map::value\_compare](../dotnet/map-value-compare-stl-clr.md)|2 要素の値の順序のデリゲート。|  
|[map::value\_type](../dotnet/map-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[map::begin](../dotnet/map-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[map::clear](../dotnet/map-clear-stl-clr.md)|すべての要素を削除します。|  
|[map::count](../dotnet/map-count-stl-clr.md)|指定したキーに一致する要素数をカウントします。|  
|[map::empty](../dotnet/map-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[map::end](../dotnet/map-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[map::equal\_range](../dotnet/map-equal-range-stl-clr.md)|指定したキーに一致する範囲を検索します。|  
|[map::erase](../dotnet/map-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[map::find](../Topic/map::find%20\(STL-CLR\).md)|指定したキーに一致する要素を検索します。|  
|[map::insert](../dotnet/map-insert-stl-clr.md)|要素を追加します。|  
|[map::key\_comp](../dotnet/map-key-comp-stl-clr.md)|2 種類のキーの順序のデリゲートをコピーします。|  
|[map::lower\_bound](../dotnet/map-lower-bound-stl-clr.md)|指定したキーに一致する範囲の先頭を検索します。|  
|[map::make\_value](../dotnet/map-make-value-stl-clr.md)|値オブジェクトを構築します。|  
|[map::map](../dotnet/map-map-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[map::rbegin](../dotnet/map-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[map::rend](../dotnet/map-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[map::size](../Topic/map::size%20\(STL-CLR\).md)|要素の数をカウントします。|  
|[map::swap](../dotnet/map-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[map::to\_array](../Topic/map::to_array%20\(STL-CLR\).md)|新しい配列に被制御シーケンスをコピーします。|  
|[map::upper\_bound](../dotnet/map-upper-bound-stl-clr.md)|指定したキーに一致する範囲の末尾を検索します。|  
|[map::value\_comp](../dotnet/map-value-comp-stl-clr.md)|2 要素の値の順序のデリゲートをコピーします。|  
  
|演算子|説明|  
|---------|--------|  
|[map::operator\=](../dotnet/map-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[map::operator](../dotnet/map-operator-stl-clr.md)|関連するマップされたな値にキーを割り当てます。|  
|[operator\!\= \(map\)](../dotnet/operator-inequality-map-stl-clr.md)|`map` オブジェクトが `map` の別のオブジェクトと等しくないかどうかを判定します。|  
|[operator\< \(map\)](../Topic/operator%3C%20\(map\)%20\(STL-CLR\).md)|`map` オブジェクトが `map` の別のオブジェクトより小さいかどうかを判定します。|  
|[operator\<\= \(map\)](../dotnet/operator-less-or-equal-map-stl-clr.md)|`map` オブジェクトが `map` の別のオブジェクト以下かどうかを判定します。|  
|[operator\=\= \(map\)](../dotnet/operator-equality-map-stl-clr.md)|`map` オブジェクトが `map` の別のオブジェクトと等しいかどうかを判定します。|  
|[operator\> \(map\)](../dotnet/operator-greater-than-map-stl-clr.md)|`map` オブジェクトが `map` の別のオブジェクトより大きいかどうかを判定します。|  
|[operator\>\= \(map\)](../dotnet/operator-greater-or-equal-map-stl-clr.md)|`map` オブジェクトが `map` の別のオブジェクト以上かどうかを判定します。|  
  
## インターフェイス  
  
|インターフェイス|説明|  
|--------------|--------|  
|<xref:System.ICloneable>|オブジェクトを複製します。|  
|<xref:System.Collections.IEnumerable>|要素によるシーケンス。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|指定された要素を通じてシーケンス。|  
|<xref:System.Collections.Generic.ICollection%601>|指定された要素のグループを保持します。|  
|<xref:System.Collections.Generic.IDictionary%602>|{}値、キー ペアのグループを保持します。|  
|ITreeKey\<の値\>|一般的なコンテナーを保持します。|  
  
## 解説  
 オブジェクトは、個々のノードとして被制御シーケンスに対するストレージの割り当て。  これは a に他方に 1 ノードの内容をコピーして、要素 \(ほとんど\) は、分散を実行しません。ノード間のリンクの変更に並べるさせてツリーで、挿入されません。  これはブロックの最初の要素を除いた要素を自由に挿入および削除できることを意味します。  
  
 オブジェクトの型は [map::key\_compare](../dotnet/map-key-compare-stl-clr.md)の格納されたデリゲート オブジェクトを呼び出すことによって制御されるシーケンスを並べ替えます。  マップを構築するときに格納されたデリゲート オブジェクトを指定する; デリゲート オブジェクトを指定しない場合、既定は比較 `operator<(key_type, key_type)`です。  メンバー関数 [map::key\_comp](../dotnet/map-key-comp-stl-clr.md)`()`を呼び出すことで、保存されたオブジェクトにアクセスします。  
  
 このようなデリゲート オブジェクトは型 [map::key\_type](../dotnet/map-key-type-stl-clr.md)のキーに厳密な弱い順序付けを課さなければ必要があります。  このいずれかの 2 種類のキー `X` と `Y`のメジャー、:  
  
 `key_comp()(X, Y)` は 呼び出しごとに同じブール型の結果を返します。  
  
 `key_comp()(X, Y)` が TRUE の場合、`key_comp()(Y, X)` が false である必要があります。  
  
 `key_comp()(X, Y)` が TRUE の場合、`X` は `Y`の前に並べると呼ばれます。  
  
 `!key_comp()(X, Y) && !key_comp()(Y, X)` が TRUE の場合、同じ大小関係があると `Y` は `X` と呼ばれます。  
  
 被制御シーケンスの `Y` に先行する要素 `X` では、`key_comp()(Y, X)` は false です。\(既定のデリゲート オブジェクトのキーは値でも減りません\)。[map](../dotnet/map-stl-clr.md)テンプレート クラスとは異なり、テンプレート クラス `map` オブジェクトはすべての要素のキーが一意である必要はありません。\(複数のキーは同じ大小関係を持つことができます。  
  
 各要素は、別のキーとマップされたな値が含まれます。  このシーケンスは、\(対数時間\) 要素の数の対数に比例した回数のアクションで任意の要素の参照、挿入、および削除を有効にすることで表されます。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 マップは、つまり、被制御シーケンスの要素を指定する反復子を持つ隣接する要素にステップ インできる双方向の反復子がサポートされています。  特別なヘッド ノードは [map::end](../dotnet/map-end-stl-clr.md)`()`が返す反復子に対応します。  存在する場合、被制御シーケンスの最後の要素にアクセスするためにこの反復子をデクリメントすることができます。  ヘッド ノードに到達するためにマップの反復子をインクリメントすることができます `end()`と等号を比較します。  ただし、`end()`が返す反復子を逆参照できません。  
  
 直接数値位置が、マップ要素を参照できない点に注意してください。。これはランダム アクセス反復子を必要とします。  
  
 マップの反復子は、関連するコンテナーにハンドルを格納する関連のマップ ノードへのハンドルを格納します。  関連するコンテナー オブジェクトでのみ反復子を使用できます。  マップの反復子は、関連するマップ ノードがマップに関連付けられている限り有効です。  また、有効な反復子は dereferencable です。指定した要素の値にアクセスするか、または変更するために使用できます。。これは `end()`と等しくない場合。  
  
 要素に設定するか、削除して、格納されている値のデストラクターを呼び出します。  コンテナーが破棄されると、すべての要素を消去します。  したがって、要素の型が ref クラスにあるコンテナー要素がコンテナーを重視されることを確認します。  ただし、Handles のコンテナーが `not` の要素を破棄されます。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [設定](../dotnet/set-stl-clr.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)