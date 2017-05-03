---
title: "MapView::Lookup メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::Lookup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::Lookup メソッド"
ms.assetid: 93090ac3-3f1d-4b7e-b80e-164b8c65cd29
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::Lookup メソッド
型 K の指定されたキーに関連付けられている型 V の値を取得します。  
  
## 構文  
  
```  
V Lookup(  
   K key  
);  
```  
  
#### パラメーター  
 `key`  
 MapView の要素の検索に使用するキー。`key` の型の型名は *K* です。  
  
## 戻り値  
 `key` とペアになる値。 戻り値の型は、型名 *V* です。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)