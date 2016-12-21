---
title: "deque (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/deque> ヘッダー [STL/CLR]"
  - "<deque> ヘッダー [STL/CLR]"
  - "deque クラス [STL/CLR]"
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロールとランダム アクセスを持つ要素の可変長シーケンスを記述します。  表示、ストレージの連続したブロックのように、残りの要素をコピーする必要なしに、一方の端に拡大または縮小できる要素のシーケンスを管理するために `deque` コンテナーを使用します。  したがって、`double-ended queue`を効率的に実装できます。\(したがって、名前\)。  
  
 以下の説明では `GValue` は `Value` な型が `Value^`場合、後者は ref 型である同じです。  
  
## 構文  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
#### パラメーター  
 GValue  
 被制御シーケンスの要素のジェネリック型。  
  
 値  
 被制御シーケンス内の要素の型。  
  
## メンバー  
  
|型定義|説明|  
|---------|--------|  
|[deque::const\_iterator](../Topic/deque::const_iterator%20\(STL-CLR\).md)|被制御シーケンスの定数反復子の型です。|  
|[deque::const\_reference](../dotnet/deque-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[deque::const\_reverse\_iterator](../dotnet/deque-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[deque::difference\_type](../dotnet/deque-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[deque::generic\_container](../Topic/deque::generic_container%20\(STL-CLR\).md)|コンテナーのジェネリック インターフェイスの種類。|  
|[deque::generic\_iterator](../dotnet/deque-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[deque::generic\_reverse\_iterator](../Topic/deque::generic_reverse_iterator%20\(STL-CLR\).md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[deque::generic\_value](../Topic/deque::generic_value%20\(STL-CLR\).md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[deque::iterator](../dotnet/deque-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[deque::reference](../dotnet/deque-reference-stl-clr.md)|要素への参照の型です。|  
|[deque::reverse\_iterator](../dotnet/deque-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[deque::size\_type](../dotnet/deque-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[deque::value\_type](../Topic/deque::value_type%20\(STL-CLR\).md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[deque::assign](../dotnet/deque-assign-stl-clr.md)|すべての要素を置き換えます。|  
|[deque::at](../dotnet/deque-at-stl-clr.md)|指定した位置にある要素にアクセスします。|  
|[deque::back](../dotnet/deque-back-stl-clr.md)|最後の要素にアクセスします。|  
|[deque::begin](../dotnet/deque-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[deque::clear](../dotnet/deque-clear-stl-clr.md)|すべての要素を削除します。|  
|[deque::deque](../dotnet/deque-deque-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[deque::empty](../dotnet/deque-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[deque::end](../Topic/deque::end%20\(STL-CLR\).md)|被制御シーケンスの末尾を指定します。|  
|[deque::erase](../Topic/deque::erase%20\(STL-CLR\).md)|指定した位置にある要素を削除します。|  
|[deque::front](../Topic/deque::front%20\(STL-CLR\).md)|最初の要素にアクセスします。|  
|[deque::insert](../dotnet/deque-insert-stl-clr.md)|指定した位置の要素を追加します。|  
|[deque::pop\_back](../dotnet/deque-pop-back-stl-clr.md)|最後の要素を削除します。|  
|[deque::pop\_front](../dotnet/deque-pop-front-stl-clr.md)|最初の要素を削除します。|  
|[deque::push\_back](../dotnet/deque-push-back-stl-clr.md)|新しい最後の要素を追加します。|  
|[deque::push\_front](../dotnet/deque-push-front-stl-clr.md)|新しい先頭要素を追加します。|  
|[deque::rbegin](../dotnet/deque-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[deque::rend](../Topic/deque::rend%20\(STL-CLR\).md)|反転被制御シーケンスの末尾を指定します。|  
|[deque::resize](../dotnet/deque-resize-stl-clr.md)|要素の数を変更します。|  
|[deque::size](../Topic/deque::size%20\(STL-CLR\).md)|要素の数をカウントします。|  
|[deque::swap](../dotnet/deque-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[deque::to\_array](../dotnet/deque-to-array-stl-clr.md)|新しい配列に被制御シーケンスをコピーします。|  
  
|プロパティ|説明|  
|-----------|--------|  
|[deque::back\_item](../Topic/deque::back_item%20\(STL-CLR\).md)|最後の要素にアクセスします。|  
|[deque::front\_item](../dotnet/deque-front-item-stl-clr.md)|最初の要素にアクセスします。|  
  
|演算子|説明|  
|---------|--------|  
|[deque::operator\!\=](../dotnet/deque-operator-inequality-stl-clr.md)|`deque` の 2 種類のオブジェクトが異なるかどうかを判定します。|  
|[deque::operator](../Topic/deque::operator\(STL-CLR\).md)|指定した位置にある要素にアクセスします。|  
|[operator\< \(deque\)](../dotnet/operator-less-than-deque-stl-clr.md)|`deque` オブジェクトが `deque` の別のオブジェクトより小さいかどうかを判定します。|  
|[operator\<\= \(deque\)](../dotnet/operator-less-or-equal-deque-stl-clr.md)|`deque` オブジェクトが `deque` の別のオブジェクト以下かどうかを判定します。|  
|[operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator\=\= \(deque\)](../dotnet/operator-equality-deque-stl-clr.md)|`deque` オブジェクトが `deque` の別のオブジェクトと等しいかどうかを判定します。|  
|[operator\> \(deque\)](../dotnet/operator-greater-than-deque-stl-clr.md)|`deque` オブジェクトが `deque` の別のオブジェクトより大きいかどうかを判定します。|  
|[operator\>\= \(deque\)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)|`deque` オブジェクトが `deque` の別のオブジェクト以上かどうかを判定します。|  
  
## インターフェイス  
  
|インターフェイス|説明|  
|--------------|--------|  
|<xref:System.ICloneable>|オブジェクトを複製します。|  
|<xref:System.Collections.IEnumerable>|要素によるシーケンス。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|指定された要素を通じてシーケンス。|  
|<xref:System.Collections.Generic.ICollection%601>|指定された要素のグループを保持します。|  
|<xref:System.Collections.Generic.IList%601>|指定された要素の順序付けグループを保持します。|  
|IDequeValue\<\>|一般的なコンテナーを保持します。|  
  
## 解説  
 オブジェクトは `Value` 要素ピッカー ブロック ハンドルの格納された配列によって制御されるシーケンスに対するストレージ領域を割り当てます。  配列は、オンデマンドで増加します。  increase は新しい要素を追加するまたは追加コストが定数時間である、残りの要素はそのままですように実行されます。  また、const 時間、およびブロックの残りの要素のないいずれかの側の要素を削除できます。  したがって、deque は [キュー](../Topic/queue%20\(STL-CLR\).md) テンプレート クラス [スタック](../dotnet/stack-stl-clr.md)の基になるコンテナーにすることをお勧めします。  
  
 つまり、直接最初の \(詳細\) 要素のゼロからカウント ダウン最後の \(戻る\) 要素の [deque::size](../Topic/deque::size%20\(STL-CLR\).md)`() - 1` に数値位置がある要素を参照できる `deque` のオブジェクトがのランダム アクセス反復子。  deque がテンプレート クラス [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)の基になるコンテナーにふさわしい候補であることを意味します。  
  
 deque の反復子は、指定した要素のバイアスとともに関連付けられた deque オブジェクトへのハンドルを格納します。  関連するコンテナー オブジェクトでのみ反復子を使用できます。  deque 要素のバイアスは位置と必ずしも同じ `not` です。  挿入された最初の要素にバイアス ゼロがあり、次のタグ付き要素にバイアス値 1 がありますが、次のアタッチされた要素にバイアス値 \-1 があります。  
  
 どちらの端に要素を挿入したりオフにしたりすることは `not` を呼び出す任意の有効なバイアスに格納される要素の値を表示します。  ただし、内部要素を挿入するか、オフに `can` の変更は、特定のバイアスに格納される要素の値、反復子プロパティで指定された値を変更できます。\(ホールを挿入する前に作成するか、消去の後に穴を満たすためにコンテナーは要素を上下にコピーする必要があります\)。いずれにしても、deque の反復子は、バイアスが有効な要素を指定すると有効になります。  また、有効な反復子は dereferencable です。指定した要素の値にアクセスするか、または変更するために使用できます。。バイアスが `end()`が返す反復子のバイアス値と等しくない場合。  
  
 要素に設定するか、削除して、格納されている値のデストラクターを呼び出します。  コンテナーが破棄されると、すべての要素を消去します。  したがって、要素の型が ref クラスにあるコンテナー要素がコンテナーを重視されることを確認します。  ただし、Handles のコンテナーが `not` の要素を破棄されます。  
  
## 必要条件  
 **ヘッダー:** \<cliext\/deque\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [一覧](../dotnet/list-stl-clr.md)   
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [キュー](../Topic/queue%20\(STL-CLR\).md)   
 [スタック](../dotnet/stack-stl-clr.md)   
 [ベクター](../dotnet/vector-stl-clr.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)