---
title: "UnorderedMapView::Lookup メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::Lookup"
ms.assetid: 22f61824-ba8c-4b8c-9077-7577c41a6742
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::Lookup メソッド
型 K の指定されたキーに関連付けられている型 V の値を取得します。  
  
## 構文  
  
```cpp  
V Lookup(  
   K key  
);  
```  
  
#### パラメーター  
 `key`  
 UnorderedMapView の要素の検索に使用するキー。`key` の型は型名 *K* です。  
  
## 戻り値  
 `key` とペアになる値。 戻り値の型は、型名 *V* です。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)