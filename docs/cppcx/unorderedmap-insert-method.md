---
title: "UnorderedMap::Insert メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::Insert"
ms.assetid: 89d55301-3cad-4877-825b-35096a1dd740
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::Insert メソッド
指定したキー\/値ペアを現在の UnorderedMap オブジェクトに追加します。  
  
## 構文  
  
```cpp  
  
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
 現在のマップ内の既存要素のキーが `true` と一致し、その要素の値部分が `key` に設定されている場合は `value`。 現在のマップ内の既存要素が `false` と一致せず、`key` および `key` パラメーターがキー\/値ペアになっていて、現在の UnorderedMap に追加されている場合は `value`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections