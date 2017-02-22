---
title: "stack (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/stack> ヘッダー [STL/CLR]"
  - "<stack> ヘッダー [STL/CLR]"
  - "stack クラス [STL/CLR]"
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# stack (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトをコントロール、後入れ先出し \(LIFO\) アクセスを持つ要素の可変長シーケンスを記述します。  後で入れ子になったコレクション型スタックとして基になるコンテナーを管理するためにコンテナーのアダプター `stack` を使用します。  
  
 以下の説明では `GValue` は `Value` な型が `Value^`場合、後者は ref 型である同じです。  同様に、`GContainer` は `Container` な型が `Container^`場合、後者は ref 型である同じです。  
  
## 構文  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
    { ..... };  
```  
  
#### パラメーター  
 値  
 被制御シーケンス内の要素の型。  
  
 \[コンテナー\]  
 基になるコンテナーの型。  
  
## メンバー  
  
|型定義|説明|  
|---------|--------|  
|[stack::const\_reference](../dotnet/stack-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[stack::container\_type](../dotnet/stack-container-type-stl-clr.md)|基になるコンテナーの型。|  
|[stack::difference\_type](../dotnet/stack-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[stack::generic\_container](../Topic/stack::generic_container%20\(STL-CLR\).md)|コンテナーのアダプターのジェネリック インターフェイスの種類。|  
|[stack::generic\_value](../dotnet/stack-generic-value-stl-clr.md)|コンテナーのアダプターのジェネリック インターフェイスの要素の型。|  
|[stack::reference](../dotnet/stack-reference-stl-clr.md)|要素への参照の型です。|  
|[stack::size\_type](../dotnet/stack-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[stack::value\_type](../dotnet/stack-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[stack::assign](../Topic/stack::assign%20\(STL-CLR\).md)|すべての要素を置き換えます。|  
|[stack::empty](../dotnet/stack-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[stack::get\_container](../Topic/stack::get_container%20\(STL-CLR\).md)|基になるコンテナーにアクセスします。|  
|[stack::pop](../Topic/stack::pop%20\(STL-CLR\).md)|最後の要素を削除します。|  
|[stack::push](../dotnet/stack-push-stl-clr.md)|新しい最後の要素を追加します。|  
|[stack::size](../dotnet/stack-size-stl-clr.md)|要素の数をカウントします。|  
|[stack::stack](../dotnet/stack-stack-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[stack::top](../dotnet/stack-top-stl-clr.md)|最後の要素にアクセスします。|  
|[stack::to\_array](../dotnet/stack-to-array-stl-clr.md)|新しい配列に被制御シーケンスをコピーします。|  
  
|プロパティ|説明|  
|-----------|--------|  
|[stack::top\_item](../dotnet/stack-top-item-stl-clr.md)|最後の要素にアクセスします。|  
  
|演算子|説明|  
|---------|--------|  
|[stack::operator\=](../dotnet/stack-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator\!\= \(stack\)](../dotnet/operator-inequality-stack-stl-clr.md)|`stack` オブジェクトが `stack` の別のオブジェクトと等しくないかどうかを判定します。|  
|[operator\< \(stack\)](../dotnet/operator-less-than-stack-stl-clr.md)|`stack` オブジェクトが `stack` の別のオブジェクトより小さいかどうかを判定します。|  
|[operator\<\= \(stack\)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|`stack` オブジェクトが `stack` の別のオブジェクト以下かどうかを判定します。|  
|[operator\=\= \(stack\)](../dotnet/operator-equality-stack-stl-clr.md)|`stack` オブジェクトが `stack` の別のオブジェクトと等しいかどうかを判定します。|  
|[operator\> \(stack\)](../dotnet/operator-greater-than-stack-stl-clr.md)|`stack` オブジェクトが `stack` の別のオブジェクトより大きいかどうかを判定します。|  
|[operator\>\= \(stack\)](../Topic/operator%3E=%20\(stack\)%20\(STL-CLR\).md)|`stack` オブジェクトが `stack` の別のオブジェクト以上かどうかを判定します。|  
  
## インターフェイス  
  
|インターフェイス|説明|  
|--------------|--------|  
|<xref:System.ICloneable>|オブジェクトを複製します。|  
|IStackValue\<のコンテナー\>|一般的なコンテナーのアダプターを保持します。|  
  
## 解説  
 オブジェクトは、基になるコンテナーを通じて被制御シーケンスに対するストレージの `Value` 要素を保存し、必要に応じて拡大、型 `Container`の割り当て。  オブジェクトは、後入れ先出し \(LIFO\) キュー \(LIFO、キュー、スタック\) を実装する、最後の要素を押しながらポップすることへのアクセスを制限します。  
  
## 必要条件  
 **ヘッダー:** \<cliext とスタック\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [deque](../dotnet/deque-stl-clr.md)   
 [一覧](../dotnet/list-stl-clr.md)   
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [キュー](../Topic/queue%20\(STL-CLR\).md)   
 [ベクター](../dotnet/vector-stl-clr.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)