---
title: "Map::Map コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Map コンストラクター"
ms.assetid: 4cd314eb-e3e3-4fa7-8c58-96e48d167246
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Map コンストラクター
マップ クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
explicit Map(  
   const C& comp = C()  
);  
explicit Map(  
   const StdMap& m  
);  
explicit Map(  
   StdMap&& m  
);  
template <  
   typename InIt  
>  
Map(  
   InItfirst,  
   InItlast,  
   const C& comp = C()  
);  
```  
  
#### パラメーター  
 `InIt`  
 現在のマップの型名。  
  
 `comp`  
 並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。  
  
 `m`  
 現在のマップを初期化するために使用される [左辺値と右辺値](http://msdn.microsoft.com/library/a8843344-cccc-40be-b701-b71f7b5cdcaf) への参照、または [map クラス](../standard-library/map-class.md)。  
  
 `first`  
 現在のマップを初期化するために使用される要素の範囲内の最初の要素の入力反復子。  
  
 `last`  
 現在のマップを初期化するために使用される要素の範囲の後の最初の要素の入力反復子。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)