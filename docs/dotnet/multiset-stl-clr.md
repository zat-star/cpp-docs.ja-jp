---
title: "multiset (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/set> ヘッダー [STL/CLR]"
  - "<set> ヘッダー [STL/CLR]"
  - "multiset クラス [STL/CLR]"
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロールと双方向アクセスできる要素の可変長シーケンスを記述します。  a として要素のシーケンスを管理するには、コンテナー `multiset` \(ほとんど\) バランスをとりましたノードの順序が指定された、ツリー、保存の 1 要素を使用します。  
  
 以下の説明では `GValue` は `GKey`な型が `Key^`場合、後者は ref 型である `Key` と同じの場合と同じです。  
  
## 構文  
  
```  
template<typename Key>  
    ref class multiset  
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
  
## メンバー  
  
|型定義|説明|  
|---------|--------|  
|[multiset::const\_iterator](../dotnet/multiset-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[multiset::const\_reference](../dotnet/multiset-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[multiset::const\_reverse\_iterator](../dotnet/multiset-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[multiset::difference\_type](../dotnet/multiset-difference-type-stl-clr.md)|2 個の要素間の a \(場合に署名する\) 間隔の種類。|  
|[multiset::generic\_container](../dotnet/multiset-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの種類。|  
|[multiset::generic\_iterator](../Topic/multiset::generic_iterator%20\(STL-CLR\).md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[multiset::generic\_reverse\_iterator](../Topic/multiset::generic_reverse_iterator%20\(STL-CLR\).md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[multiset::generic\_value](../dotnet/multiset-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[multiset::iterator](../dotnet/multiset-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md)|2 種類のキーの順序のデリゲート。|  
|[multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md)|順序付けキーの型です。|  
|[multiset::reference](../dotnet/multiset-reference-stl-clr.md)|要素への参照の型です。|  
|[multiset::reverse\_iterator](../dotnet/multiset-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[multiset::size\_type](../dotnet/multiset-size-type-stl-clr.md)|2 個の要素間の a \(負\) 間隔の種類。|  
|[multiset::value\_compare](../Topic/multiset::value_compare%20\(STL-CLR\).md)|2 要素の値の順序のデリゲート。|  
|[multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[multiset::begin](../dotnet/multiset-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[multiset::clear](../dotnet/multiset-clear-stl-clr.md)|すべての要素を削除します。|  
|[multiset::count](../dotnet/multiset-count-stl-clr.md)|指定したキーに一致する要素数をカウントします。|  
|[multiset::empty](../dotnet/multiset-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[multiset::end](../dotnet/multiset-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[multiset::equal\_range](../dotnet/multiset-equal-range-stl-clr.md)|指定したキーに一致する範囲を検索します。|  
|[multiset::erase](../dotnet/multiset-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[multiset::find](../Topic/multiset::find%20\(STL-CLR\).md)|指定したキーに一致する要素を検索します。|  
|[multiset::insert](../Topic/multiset::insert%20\(STL-CLR\).md)|要素を追加します。|  
|[multiset::key\_comp](../Topic/multiset::key_comp%20\(STL-CLR\).md)|2 種類のキーの順序のデリゲートをコピーします。|  
|[multiset::lower\_bound](../Topic/multiset::lower_bound%20\(STL-CLR\).md)|指定したキーに一致する範囲の先頭を検索します。|  
|[multiset::make\_value](../Topic/multiset::make_value%20\(STL-CLR\).md)|値オブジェクトを構築します。|  
|[multiset::multiset](../dotnet/multiset-multiset-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[multiset::rbegin](../dotnet/multiset-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[multiset::rend](../Topic/multiset::rend%20\(STL-CLR\).md)|反転被制御シーケンスの末尾を指定します。|  
|[multiset::size](../dotnet/multiset-size-stl-clr.md)|要素の数をカウントします。|  
|[multiset::swap](../dotnet/multiset-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[multiset::to\_array](../dotnet/multiset-to-array-stl-clr.md)|新しい配列に被制御シーケンスをコピーします。|  
|[multiset::upper\_bound](../dotnet/multiset-upper-bound-stl-clr.md)|指定したキーに一致する範囲の末尾を検索します。|  
|[multiset::value\_comp](../dotnet/multiset-value-comp-stl-clr.md)|2 要素の値の順序のデリゲートをコピーします。|  
  
|演算子|説明|  
|---------|--------|  
|[multiset::operator\=](../dotnet/multiset-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator\!\= \(multiset\)](../dotnet/operator-inequality-multiset-stl-clr.md)|`multiset` オブジェクトが `multiset` の別のオブジェクトと等しくないかどうかを判定します。|  
|[operator\< \(multiset\)](../dotnet/operator-less-than-multiset-stl-clr.md)|`multiset` オブジェクトが `multiset` の別のオブジェクトより小さいかどうかを判定します。|  
|[operator\<\= \(multiset\)](../Topic/operator%3C=%20\(multiset\)%20\(STL-CLR\).md)|`multiset` オブジェクトが `multiset` の別のオブジェクト以下かどうかを判定します。|  
|[operator\=\= \(multiset\)](../Topic/operator==%20\(multiset\)%20\(STL-CLR\).md)|`multiset` オブジェクトが `multiset` の別のオブジェクトと等しいかどうかを判定します。|  
|[operator\> \(multiset\)](../dotnet/operator-greater-than-multiset-stl-clr.md)|`multiset` オブジェクトが `multiset` の別のオブジェクトより大きいかどうかを判定します。|  
|[operator\>\= \(multiset\)](../Topic/operator%3E=%20\(multiset\)%20\(STL-CLR\).md)|`multiset` オブジェクトが `multiset` の別のオブジェクト以上かどうかを判定します。|  
  
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
  
 オブジェクトの型は [multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md)の格納されたデリゲート オブジェクトを呼び出すことによって制御されるシーケンスを並べ替えます。  マルチセットを構築するときに格納されたデリゲート オブジェクトを指定する; デリゲート オブジェクトを指定しない場合、既定は比較 `operator<(key_type, key_type)`です。  メンバー関数 [multiset::key\_comp](../Topic/multiset::key_comp%20\(STL-CLR\).md)`()`を呼び出すことで、保存されたオブジェクトにアクセスします。  
  
 このようなデリゲート オブジェクトは型 [multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md)のキーに厳密な弱い順序付けを課さなければ必要があります。  このいずれかの 2 種類のキー `X` と `Y`のメジャー、:  
  
 `key_comp()(X, Y)` は 呼び出しごとに同じブール型の結果を返します。  
  
 `key_comp()(X, Y)` が TRUE の場合、`key_comp()(Y, X)` が false である必要があります。  
  
 `key_comp()(X, Y)` が TRUE の場合、`X` は `Y`の前に並べると呼ばれます。  
  
 `!key_comp()(X, Y) && !key_comp()(Y, X)` が TRUE の場合、同じ大小関係があると `Y` は `X` と呼ばれます。  
  
 被制御シーケンスの `Y` に先行する要素 `X` では、`key_comp()(Y, X)` は false です。\(既定のデリゲート オブジェクトのキーは値でも減りません\)。[設定](../dotnet/set-stl-clr.md)テンプレート クラスとは異なり、テンプレート クラス `multiset` オブジェクトはすべての要素のキーが一意である必要はありません。\(複数のキーは同じ大小関係を持つことができます。  
  
 各要素は ey と値として機能します。  このシーケンスは、\(対数時間\) 要素の数の対数に比例した回数のアクションで任意の要素の参照、挿入、および削除を有効にすることで表されます。  要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 マルチセットはメジャーは、被制御シーケンスの要素を指定する反復子を持つ隣接する要素にステップ インできる双方向の反復子がサポートされています。  特別なヘッド ノードは [multiset::end](../dotnet/multiset-end-stl-clr.md)`()`が返す反復子に対応します。  存在する場合、被制御シーケンスの最後の要素にアクセスするためにこの反復子をデクリメントすることができます。  ヘッド ノードに到達するためにマルチセットの反復子をインクリメントすることができます `end()`と等号を比較します。  ただし、`end()`が返す反復子を逆参照できません。  
  
 直接数値位置が、マルチセットの要素を参照できないことに注意してください。。これはランダム アクセス反復子を必要とします。  
  
 マルチセットの反復子は、関連するコンテナーにハンドルを格納する関連付けられたマルチセット ノードへのハンドルを格納します。  関連するコンテナー オブジェクトでのみ反復子を使用できます。  マルチセットの反復子は、関連するマルチセット ノードがマルチセットに関連付けられている限り有効です。  また、有効な反復子は dereferencable です。指定した要素の値にアクセスするか、または変更するために使用できます。。これは `end()`と等しくない場合。  
  
 要素に設定するか、削除して、格納されている値のデストラクターを呼び出します。  コンテナーが破棄されると、すべての要素を消去します。  したがって、要素の型が ref クラスにあるコンテナー要素がコンテナーを重視されることを確認します。  ただし、Handles のコンテナーが `not` の要素を破棄されます。  
  
## 必要条件  
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [マップ](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [設定](../dotnet/set-stl-clr.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)