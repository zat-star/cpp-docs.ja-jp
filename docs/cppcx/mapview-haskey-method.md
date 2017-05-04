---
title: "MapView::HasKey メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::HasKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::HasKey メソッド"
ms.assetid: c1a24f63-e6fd-4cfd-90ce-b89352b98324
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::HasKey メソッド
現在の MapView に、指定されたキーが含まれているかどうかを判定します。  
  
## 構文  
  
```  
  
bool HasKey(  
   K key  
);  
```  
  
#### パラメーター  
 `key`  
 MapView 要素の検索に使用するキー。`key` の型は型名 *K* です。  
  
## 戻り値  
 キーが見つかった場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)