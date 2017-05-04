---
title: "Map::Insert メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Insert"
ms.assetid: 3acb2221-c12f-407a-a570-2e52df3569f6
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Insert メソッド
指定したキー\/値ペアを現在のマップ オブジェクトに追加します。  
  
## 構文  
  
```  
  
virtual bool Insert(  
   K key,   
   V value  
);  
```  
  
#### パラメーター  
 `key`  
 キー\/値ペアのキー部分。`key` の型は型名 *K* です。  
  
 `value`  
 キー\/値ペアの値部分。`value` の型は型名 *V* です。  
  
## 戻り値  
 現在のマップ内の既存要素のキーが `true` と一致し、その要素の値部分が `key` に設定されている場合は `value`。 現在のマップ内の既存要素が `false` と一致せず、`key` および `key` パラメーターがキー\/値ペアになっていて、現在のマップに追加されている場合は `value`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)