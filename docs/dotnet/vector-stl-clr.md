---
title: "vector (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/vector> ヘッダー [STL/CLR]"
  - "<vector> ヘッダー [STL/CLR]"
  - "vector クラス [STL/CLR]"
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロールとランダム アクセスを持つ要素の可変長シーケンスを記述します。  ストレージの連続したブロックとして要素のシーケンスを管理するために `vector` コンテナーを使用します。  ブロックは、オンデマンドを越える配列として実装されます。  
  
 以下の説明では `GValue` は `Value` な型が `Value^`場合、後者は ref 型である同じです。  
  
## 構文  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### パラメーター  
 値  
 被制御シーケンス内の要素の型。  
  
## メンバー  
  
|型定義|説明|  
|---------|--------|  
|[vector::const\_iterator](../dotnet/vector-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[vector::const\_reference](../dotnet/vector-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[vector::const\_reverse\_iterator](../dotnet/vector-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[vector::difference\_type](../dotnet/vector-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの種類。|  
|[vector::generic\_iterator](../dotnet/vector-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[vector::generic\_reverse\_iterator](../Topic/vector::generic_reverse_iterator%20\(STL-CLR\).md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[vector::generic\_value](../dotnet/vector-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[vector::iterator](../dotnet/vector-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[vector::reference](../dotnet/vector-reference-stl-clr.md)|要素への参照の型です。|  
|[vector::reverse\_iterator](../dotnet/vector-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[vector::size\_type](../dotnet/vector-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[vector::value\_type](../Topic/vector::value_type%20\(STL-CLR\).md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[vector::assign](../Topic/vector::assign%20\(STL-CLR\).md)|すべての要素を置き換えます。|  
|[vector::at](../dotnet/vector-at-stl-clr.md)|指定した位置にある要素にアクセスします。|  
|[vector::back](../dotnet/vector-back-stl-clr.md)|最後の要素にアクセスします。|  
|[vector::begin](../dotnet/vector-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[vector::capacity](../dotnet/vector-capacity-stl-clr.md)|コンテナーに割り当てられたストレージの容量を報告します。|  
|[vector::clear](../dotnet/vector-clear-stl-clr.md)|すべての要素を削除します。|  
|[vector::empty](../Topic/vector::empty%20\(STL-CLR\).md)|要素が存在しないかどうかをテストします。|  
|[vector::end](../dotnet/vector-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[vector::erase](../dotnet/vector-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[vector::front](../dotnet/vector-front-stl-clr.md)|最初の要素にアクセスします。|  
|[vector::insert](../Topic/vector::insert%20\(STL-CLR\).md)|指定した位置の要素を追加します。|  
|[vector::pop\_back](../Topic/vector::pop_back%20\(STL-CLR\).md)|最後の要素を削除します。|  
|[vector::push\_back](../dotnet/vector-push-back-stl-clr.md)|新しい最後の要素を追加します。|  
|[vector::rbegin](../dotnet/vector-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[vector::rend](../dotnet/vector-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[vector::reserve](../Topic/vector::reserve%20\(STL-CLR\).md)|コンテナーの最小の増加容量を確認します。|  
|[vector::resize](../Topic/vector::resize%20\(STL-CLR\).md)|要素の数を変更します。|  
|[vector::size](../dotnet/vector-size-stl-clr.md)|要素の数をカウントします。|  
|[vector::swap](../dotnet/vector-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[vector::to\_array](../dotnet/vector-to-array-stl-clr.md)|新しい配列に被制御シーケンスをコピーします。|  
|[vector::vector](../dotnet/vector-vector-stl-clr.md)|コンテナー オブジェクトを構築します。|  
  
|プロパティ|説明|  
|-----------|--------|  
|[vector::back\_item](../dotnet/vector-back-item-stl-clr.md)|最後の要素にアクセスします。|  
|[vector::front\_item](../dotnet/vector-front-item-stl-clr.md)|最初の要素にアクセスします。|  
  
|演算子|説明|  
|---------|--------|  
|[vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[vector::operator](../dotnet/vector-operator-stl-clr.md)|指定した位置にある要素にアクセスします。|  
|[operator\!\= \(vector\)](../Topic/operator!=%20\(vector\)%20\(STL-CLR\).md)|`vector` オブジェクトが `vector` の別のオブジェクトと等しくないかどうかを判定します。|  
|[operator\< \(vector\)](../dotnet/operator-less-than-vector-stl-clr.md)|`vector` オブジェクトが `vector` の別のオブジェクトより小さいかどうかを判定します。|  
|[operator\<\= \(vector\)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|`vector` オブジェクトが `vector` の別のオブジェクト以下かどうかを判定します。|  
|[operator\=\= \(vector\)](../Topic/operator==%20\(vector\)%20\(STL-CLR\).md)|`vector` オブジェクトが `vector` の別のオブジェクトと等しいかどうかを判定します。|  
|[operator\> \(vector\)](../dotnet/operator-greater-than-vector-stl-clr.md)|`vector` オブジェクトが `vector` の別のオブジェクトより大きいかどうかを判定します。|  
|[operator\>\= \(vector\)](../Topic/operator%3E=%20\(vector\)%20\(STL-CLR\).md)|`vector` オブジェクトが `vector` の別のオブジェクト以上かどうかを判定します。|  
  
## インターフェイス  
  
|インターフェイス|説明|  
|--------------|--------|  
|<xref:System.ICloneable>|オブジェクトを複製します。|  
|<xref:System.Collections.IEnumerable>|要素によるシーケンス。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|指定された要素を通じてシーケンス。|  
|<xref:System.Collections.Generic.ICollection%601>|指定された要素のグループを保持します。|  
|<xref:System.Collections.Generic.IList%601>|指定された要素の順序付けグループを保持します。|  
|IVectorValue\<\>|一般的なコンテナーを保持します。|  
  
## 解説  
 オブジェクトは、オンデマンドで表示され、`Value` 要素に格納された配列によって制御されるシーケンスに対するストレージ領域を割り当てます。  increase は新しい要素を付けるコストが定数時間償却されるようにします。  つまり、末尾に要素を追加すると、被制御シーケンスの長さを大きくすると、平均すると向上しません。  そのため、ベクターは、テンプレート クラス [スタック](../dotnet/stack-stl-clr.md)の基になるコンテナーにすることをお勧めします。  
  
 `vector` を意味が直接最初の \(詳細\) 要素のゼロからカウント ダウン最後の \(戻る\) 要素の [vector::size](../dotnet/vector-size-stl-clr.md)`() - 1` に数値位置がある要素を参照できるランダム アクセス反復子がサポートされています。  ベクターがテンプレート クラス [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)の基になるコンテナーにふさわしい候補であることを意味します。  
  
 ベクターの反復子は、指定した要素のバイアスとともに関連するベクター オブジェクトへのハンドルを格納します。  関連するコンテナー オブジェクトでのみ反復子を使用できます。  ベクター要素のバイアスは位置と同じになります。  
  
 要素を挿入したりオフにしたりすることで、指定した位置に格納される要素の値を変更して、反復子で指定される値も変更できます。\(ホールを挿入する前に作成するか、消去の後に穴を満たすためにコンテナーは要素を上下にコピーする必要があります\)。いずれにしても、ベクターの反復子は、バイアス値が範囲 `[0,`[vector::size](../dotnet/vector-size-stl-clr.md)`()]`に限り有効です。  また、有効な反復子は dereferencable です。指定した要素の値にアクセスするか、または変更するために使用できます。。バイアスが `size()`と等しくない場合。  
  
 要素に設定するか、削除して、格納されている値のデストラクターを呼び出します。  コンテナーが破棄されると、すべての要素を消去します。  したがって、要素の型が ref クラスにあるコンテナー要素がコンテナーを重視されることを確認します。  ただし、Handles のコンテナーが `not` の要素を破棄されます。  
  
## 必要条件  
 **ヘッダー:** の \<cliext とベクター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [deque](../dotnet/deque-stl-clr.md)   
 [一覧](../dotnet/list-stl-clr.md)   
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [キュー](../Topic/queue%20\(STL-CLR\).md)   
 [スタック](../dotnet/stack-stl-clr.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)