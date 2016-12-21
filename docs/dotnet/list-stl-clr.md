---
title: "list (STL/CLR) | Microsoft Docs"
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
  - "cliext::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/list> ヘッダー [STL/CLR]"
  - "<list> ヘッダー [STL/CLR]"
  - "list クラス [STL/CLR]"
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロールと双方向アクセスできる要素の可変長シーケンスを記述します。  ノードの双方向リンク リスト、保存の 1 要素として要素のシーケンスを管理するために `list` コンテナーを使用します。  
  
 以下の説明では `GValue` は `Value` な型が `Value^`場合、後者は ref 型である同じです。  
  
## 構文  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### パラメーター  
 値  
 被制御シーケンス内の要素の型。  
  
## メンバー  
  
|型定義|説明|  
|---------|--------|  
|[list::const\_iterator](../dotnet/list-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[list::const\_reference](../dotnet/list-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[list::const\_reverse\_iterator](../dotnet/list-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[list::difference\_type](../dotnet/list-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[list::generic\_container](../dotnet/list-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの種類。|  
|[list::generic\_iterator](../Topic/list::generic_iterator%20\(STL-CLR\).md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[list::generic\_reverse\_iterator](../dotnet/list-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[list::generic\_value](../dotnet/list-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[list::iterator](../dotnet/list-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[list::reference](../dotnet/list-reference-stl-clr.md)|要素への参照の型です。|  
|[list::reverse\_iterator](../dotnet/list-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[list::size\_type](../dotnet/list-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[list::value\_type](../dotnet/list-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[list::assign](../dotnet/list-assign-stl-clr.md)|すべての要素を置き換えます。|  
|[list::back](../dotnet/list-back-stl-clr.md)|最後の要素にアクセスします。|  
|[list::begin](../Topic/list::begin%20\(STL-CLR\).md)|被制御シーケンスの先頭を指定します。|  
|[list::clear](../dotnet/list-clear-stl-clr.md)|すべての要素を削除します。|  
|[list::empty](../dotnet/list-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[list::end](../Topic/list::end%20\(STL-CLR\).md)|被制御シーケンスの末尾を指定します。|  
|[list::erase](../dotnet/list-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[list::front](../dotnet/list-front-stl-clr.md)|最初の要素にアクセスします。|  
|[list::insert](../dotnet/list-insert-stl-clr.md)|指定した位置の要素を追加します。|  
|[list::list](../dotnet/list-list-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[list::merge](../dotnet/list-merge-stl-clr.md)|2 つの順序付けされた被制御シーケンスをマージします。|  
|[list::pop\_back](../dotnet/list-pop-back-stl-clr.md)|最後の要素を削除します。|  
|[list::pop\_front](../dotnet/list-pop-front-stl-clr.md)|最初の要素を削除します。|  
|[list::push\_back](../dotnet/list-push-back-stl-clr.md)|新しい最後の要素を追加します。|  
|[list::push\_front](../Topic/list::push_front%20\(STL-CLR\).md)|新しい先頭要素を追加します。|  
|[list::rbegin](../dotnet/list-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[list::remove](../dotnet/list-remove-stl-clr.md)|指定された値に要素を削除します。|  
|[list::remove\_if](../dotnet/list-remove-if-stl-clr.md)|指定したテストに合格する要素を削除します。|  
|[list::rend](../Topic/list::rend%20\(STL-CLR\).md)|反転被制御シーケンスの末尾を指定します。|  
|[list::resize](../dotnet/list-resize-stl-clr.md)|要素の数を変更します。|  
|[list::reverse](../dotnet/list-reverse-stl-clr.md)|被制御シーケンスを反転させます。|  
|[list::size](../dotnet/list-size-stl-clr.md)|要素の数をカウントします。|  
|[list::sort](../dotnet/list-sort-stl-clr.md)|被制御シーケンスを順序付けます。|  
|[list::splice](../Topic/list::splice%20\(STL-CLR\).md)|ノード間のリンクを再接合します。|  
|[list::swap](../Topic/list::swap%20\(STL-CLR\).md)|2 つのコンテナーのコンテンツを交換します。|  
|[list::to\_array](../dotnet/list-to-array-stl-clr.md)|新しい配列に被制御シーケンスをコピーします。|  
|[list::unique](../dotnet/list-unique-stl-clr.md)|指定されたテストに合格した隣接する要素を削除します。|  
  
|プロパティ|説明|  
|-----------|--------|  
|[list::back\_item](../Topic/list::back_item%20\(STL-CLR\).md)|最後の要素にアクセスします。|  
|[list::front\_item](../dotnet/list-front-item-stl-clr.md)|最初の要素にアクセスします。|  
  
|演算子|説明|  
|---------|--------|  
|[list::operator\=](../dotnet/list-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator\!\= \(list\)](../dotnet/operator-inequality-list-stl-clr.md)|`list` オブジェクトが `list` の別のオブジェクトと等しくないかどうかを判定します。|  
|[operator\< \(list\)](../dotnet/operator-less-than-list-stl-clr.md)|`list` オブジェクトが `list` の別のオブジェクトより小さいかどうかを判定します。|  
|[operator\<\= \(list\)](../dotnet/operator-less-or-equal-list-stl-clr.md)|`list` オブジェクトが `list` の別のオブジェクト以下かどうかを判定します。|  
|[operator\=\= \(list\)](../dotnet/operator-equality-list-stl-clr.md)|`list` オブジェクトが `list` の別のオブジェクトと等しいかどうかを判定します。|  
|[operator\> \(list\)](../Topic/operator%3E%20\(list\)%20\(STL-CLR\).md)|`list` オブジェクトが `list` の別のオブジェクトより大きいかどうかを判定します。|  
|[operator\>\= \(list\)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|`list` オブジェクトが `list` の別のオブジェクト以上かどうかを判定します。|  
  
## インターフェイス  
  
|インターフェイス|説明|  
|--------------|--------|  
|<xref:System.ICloneable>|オブジェクトを複製します。|  
|<xref:System.Collections.IEnumerable>|要素によるシーケンス。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|指定された要素を通じてシーケンス。|  
|<xref:System.Collections.Generic.ICollection%601>|指定された要素のグループを保持します。|  
|IListValue\<\>|一般的なコンテナーを保持します。|  
  
## 解説  
 オブジェクトは、双方向リンクの個々のノードに追加したときに被制御シーケンスに対するストレージの割り当て。  これにより、ノード間のリンクを変更して、別の場所に 1 ノードの内容をコピーして、要素を再配置されません。  これはブロックの最初の要素を除いた要素を自由に挿入および削除できることを意味します。  したがって、リストは [キュー](../Topic/queue%20\(STL-CLR\).md) テンプレート クラス [スタック](../dotnet/stack-stl-clr.md)の基になるコンテナーにすることをお勧めします。  
  
 つまり、被制御シーケンスの要素を指定する反復子を持つ隣接する要素にステップ インできる `list` のオブジェクトが双方向の反復子。  特別なヘッド ノードは [list::end](../Topic/list::end%20\(STL-CLR\).md)`()`が返す反復子に対応します。  存在する場合、被制御シーケンスの最後の要素にアクセスするためにこの反復子をデクリメントすることができます。  ヘッド ノードに到達するリストの反復子をインクリメントすることができます `end()`と等号を比較します。  ただし、`end()`が返す反復子を逆参照できません。  
  
 直接数値位置が、リストの要素を参照できない点に注意してください。。これはランダム アクセス反復子を必要とします。  このリストは、テンプレート クラス [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)の根本的なコンテナーとして使用可能な `not` です。  
  
 リストの反復子は、関連するコンテナーにハンドルを格納する関連付けられたリスト ノードへのハンドルを格納します。  関連するコンテナー オブジェクトでのみ反復子を使用できます。  リストの反復子は、関連付けられたリスト ノードをリストに関連付けられている限り有効です。  また、有効な反復子は dereferencable です。指定した要素の値にアクセスするか、または変更するために使用できます。。これは `end()`と等しくない場合。  
  
 要素に設定するか、削除して、格納されている値のデストラクターを呼び出します。  コンテナーが破棄されると、すべての要素を消去します。  したがって、要素の型が ref クラスにあるコンテナー要素がコンテナーを重視されることを確認します。  ただし、Handles のコンテナーが `not` の要素を破棄されます。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/リスト\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [deque](../dotnet/deque-stl-clr.md)   
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [キュー](../Topic/queue%20\(STL-CLR\).md)   
 [スタック](../dotnet/stack-stl-clr.md)   
 [ベクター](../dotnet/vector-stl-clr.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)