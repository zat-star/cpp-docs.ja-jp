---
title: "MapView::MapView コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::MapView コンストラクター"
ms.assetid: 67a3250c-b527-47ac-a103-0fd186046d71
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::MapView コンストラクター
MapView クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
explicit MapView(  
    const C& comp = C()  
    );  
  
explicit MapView(  
    const ::std::map<K, V, C>& m  
    );  
  
explicit MapView(  
    std::map<K, V, C>&& m  
    );  
  
template <typename InIt> MapView(  
    InIt first,  
    InIt last,  
    const C& comp = C()  
    );  
  
MapView(::std::initializer_list<  
    std::pair<const K, V>> il,  
    const C& comp = C()  
    );  
```  
  
#### パラメーター  
 `InIt`  
 現在の MapView の型名。  
  
 `comp`  
 並べ替えキーとして 2 つの要素値を比較して MapView 内の相対順序を決定できる関数オブジェクト。  
  
 `m`  
 現在の MapView を初期化するために使用される [左辺値と右辺値](http://msdn.microsoft.com/library/a8843344-cccc-40be-b701-b71f7b5cdcaf) への参照、または [map クラス](../standard-library/map-class.md)。  
  
 `first`  
 現在の MapView を初期化するために使用される要素の範囲内の最初の要素の入力反復子。  
  
 `last`  
 現在の MapView を初期化するために使用される要素の範囲の後の最初の要素の入力反復子。  
  
 il  
 要素が MapView に挿入される [std::initializer\_list\<std::pair\<K,V\>\>](../standard-library/initializer-list-class.md)。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)