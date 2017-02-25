---
title: "multimap (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/map> ヘッダー [STL/CLR]"
  - "<map> ヘッダー [STL/CLR]"
  - "multimap クラス [STL/CLR]"
ms.assetid: 3dfe329d-a078-462a-b050-7999ce6110ad
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロールと双方向アクセスできる要素の可変長シーケンスを記述します。  a として要素のシーケンスを管理するには、コンテナー `multimap` \(ほとんど\) バランスをとりましたノードの順序が指定された、ツリー、保存の 1 要素を使用します。  要素がシーケンスを、乗車に移動マップされたな値を使用するためのキーで構成されています。  
  
 以下の説明では `GValue` は同じです:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 それぞれの文字について以下に説明します。  
  
 `GKey` は `Key` な型が `Key^`場合、後者は ref 型である同じになりますが、  
  
 `GMapped` は `Mapped` な型が `Mapped^`場合、後者は ref 型である同じになりますが、  
  
## 構文  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class multimap  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
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
|[multimap::const\_iterator](../dotnet/multimap-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[multimap::const\_reference](../dotnet/multimap-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[multimap::const\_reverse\_iterator](../Topic/multimap::const_reverse_iterator%20\(STL-CLR\).md)|被制御シーケンスの定数反転反復子の型です。|  
|[multimap::difference\_type](../dotnet/multimap-difference-type-stl-clr.md)|2 個の要素間の a \(場合に署名する\) 間隔の種類。|  
|[multimap::generic\_container](../dotnet/multimap-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの種類。|  
|[multimap::generic\_iterator](../dotnet/multimap-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[multimap::generic\_reverse\_iterator](../dotnet/multimap-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[multimap::generic\_value](../dotnet/multimap-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[multimap::iterator](../dotnet/multimap-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md)|2 種類のキーの順序のデリゲート。|  
|[multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)|順序付けキーの型です。|  
|[multimap::mapped\_type](../dotnet/multimap-mapped-type-stl-clr.md)|マップされたな値の型は、各キーに関連付けられています。|  
|[multimap::reference](../dotnet/multimap-reference-stl-clr.md)|要素への参照の型です。|  
|[multimap::reverse\_iterator](../Topic/multimap::reverse_iterator%20\(STL-CLR\).md)|被制御シーケンスの反転反復子の型です。|  
|[multimap::size\_type](../Topic/multimap::size_type%20\(STL-CLR\).md)|2 個の要素間の a \(負\) 間隔の種類。|  
|[multimap::value\_compare](../Topic/multimap::value_compare%20\(STL-CLR\).md)|2 要素の値の順序のデリゲート。|  
|[multimap::value\_type](../dotnet/multimap-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[multimap::begin](../dotnet/multimap-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[multimap::clear](../Topic/multimap::clear%20\(STL-CLR\).md)|すべての要素を削除します。|  
|[multimap::count](../dotnet/multimap-count-stl-clr.md)|指定したキーに一致する要素数をカウントします。|  
|[multimap::empty](../dotnet/multimap-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[multimap::end](../dotnet/multimap-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[multimap::equal\_range](../dotnet/multimap-equal-range-stl-clr.md)|指定したキーに一致する範囲を検索します。|  
|[multimap::erase](../dotnet/multimap-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[multimap::find](../dotnet/multimap-find-stl-clr.md)|指定したキーに一致する要素を検索します。|  
|[multimap::insert](../dotnet/multimap-insert-stl-clr.md)|要素を追加します。|  
|[multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)|2 種類のキーの順序のデリゲートをコピーします。|  
|[multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)|指定したキーに一致する範囲の先頭を検索します。|  
|[multimap::make\_value](../dotnet/multimap-make-value-stl-clr.md)|値オブジェクトを構築します。|  
|[multimap::multimap](../dotnet/multimap-multimap-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[multimap::rbegin](../dotnet/multimap-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[multimap::rend](../dotnet/multimap-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[multimap::size](../Topic/multimap::size%20\(STL-CLR\).md)|要素の数をカウントします。|  
|[multimap::swap](../dotnet/multimap-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[multimap::to\_array](../dotnet/multimap-to-array-stl-clr.md)|新しい配列に被制御シーケンスをコピーします。|  
|[multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)|指定したキーに一致する範囲の末尾を検索します。|  
|[multimap::value\_comp](../Topic/multimap::value_comp%20\(STL-CLR\).md)|2 要素の値の順序のデリゲートをコピーします。|  
  
|演算子|説明|  
|---------|--------|  
|[multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator\!\= \(multimap\)](../Topic/operator!=%20\(multimap\)%20\(STL-CLR\).md)|`multimap` オブジェクトが `multimap` の別のオブジェクトと等しくないかどうかを判定します。|  
|[operator\< \(multimap\)](../dotnet/operator-less-than-multimap-stl-clr.md)|`multimap` オブジェクトが `multimap` の別のオブジェクトより小さいかどうかを判定します。|  
|[operator\<\= \(multimap\)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)|`multimap` オブジェクトが `multimap` の別のオブジェクト以下かどうかを判定します。|  
|[operator\=\= \(multimap\)](../dotnet/operator-equality-multimap-stl-lr.md)|`multimap` オブジェクトが `multimap` の別のオブジェクトと等しいかどうかを判定します。|  
|[operator\> \(multimap\)](../dotnet/operator-greater-than-multimap-stl-clr.md)|`multimap` オブジェクトが `multimap` の別のオブジェクトより大きいかどうかを判定します。|  
|[operator\>\= \(multimap\)](../Topic/operator%3E=%20\(multimap\)%20\(STL-CLR\).md)|`multimap` オブジェクトが `multimap` の別のオブジェクト以上かどうかを判定します。|  
  
## インターフェイス  
  
|インターフェイス|説明|  
|--------------|--------|  
|<xref:System.ICloneable>|オブジェクトを複製します。|  
|<xref:System.Collections.IEnumerable>|要素によるシーケンス。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|指定された要素を通じてシーケンス。|  
|<xref:System.Collections.Generic.ICollection%601>|指定された要素のグループを保持します。|  
|ITreeKey\<の値\>|一般的なコンテナーを保持します。|  
  
## 解説  
 オブジェクトは、個々のノードとして被制御シーケンスに対するストレージの割り当て。  これは a に他方に 1 ノードの内容をコピーして、要素 \(ほとんど\) は、分散を実行しません。ノード間のリンクの変更に並べるさせてツリーで、挿入されません。  これはブロックの最初の要素を除いた要素を自由に挿入および削除できることを意味します。  
  
 オブジェクトの型は [multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md)の格納されたデリゲート オブジェクトを呼び出すことによって制御されるシーケンスを並べ替えます。  multimap を構築するときに格納されたデリゲート オブジェクトを指定する; デリゲート オブジェクトを指定しない場合、既定は比較 `operator<(key_type, key_type)`です。  メンバー関数 [multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)`()`を呼び出すことで、保存されたオブジェクトにアクセスします。  
  
 このようなデリゲート オブジェクトは型 [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)のキーに厳密な弱い順序付けを課さなければ必要があります。  このいずれかの 2 種類のキー `X` と `Y`のメジャー、:  
  
 `key_comp()(X, Y)` は 呼び出しごとに同じブール型の結果を返します。  
  
 `key_comp()(X, Y)` が TRUE の場合、`key_comp()(Y, X)` が false である必要があります。  
  
 `key_comp()(X, Y)` が TRUE の場合、`X` は `Y`の前に並べると呼ばれます。  
  
 `!key_comp()(X, Y) && !key_comp()(Y, X)` が TRUE の場合、同じ大小関係があると `Y` は `X` と呼ばれます。  
  
 被制御シーケンスの `Y` に先行する要素 `X` では、`key_comp()(Y, X)` は false です。\(既定のデリゲート オブジェクトのキーは値でも減りません\)。[マップ](../dotnet/map-stl-clr.md)テンプレート クラスとは異なり、テンプレート クラス `multimap` オブジェクトはすべての要素のキーが一意である必要はありません。\(複数のキーは同じ大小関係を持つことができます。  
  
 各要素は、別のキーとマップされたな値が含まれます。  このシーケンスは、\(対数時間\) 要素の数の対数に比例した回数のアクションで任意の要素の参照、挿入、および削除を有効にすることで表されます。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 multimap、つまり、被制御シーケンスの要素を指定する反復子を持つ隣接する要素にステップ インできる双方向の反復子がサポートされています。  特別なヘッド ノードは [multimap::end](../dotnet/multimap-end-stl-clr.md)`()`が返す反復子に対応します。  存在する場合、被制御シーケンスの最後の要素にアクセスするためにこの反復子をデクリメントすることができます。  ヘッド ノードに到達するために multimap の反復子をインクリメントすることができます `end()`と等号を比較します。  ただし、`end()`が返す反復子を逆参照できません。  
  
 直接数値位置が、multimap の要素を参照できないことに注意してください。。これはランダム アクセス反復子を必要とします。  
  
 multimap の反復子は、関連するコンテナーにハンドルを格納する関連付けられた multimap ノードへのハンドルを格納します。  関連するコンテナー オブジェクトでのみ反復子を使用できます。  multimap の反復子は、関連付けられた multimap ノードが multimap に関連付けられている限り有効です。  また、有効な反復子は dereferencable です。指定した要素の値にアクセスするか、または変更するために使用できます。。これは `end()`と等しくない場合。  
  
 要素に設定するか、削除して、格納されている値のデストラクターを呼び出します。  コンテナーが破棄されると、すべての要素を消去します。  したがって、要素の型が ref クラスにあるコンテナー要素がコンテナーを重視されることを確認します。  ただし、Handles のコンテナーが `not` の要素を破棄されます。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [マップ](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [設定](../dotnet/set-stl-clr.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)