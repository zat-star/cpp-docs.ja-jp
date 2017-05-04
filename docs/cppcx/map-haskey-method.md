---
title: "Map::HasKey メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::HasKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::HasKey メソッド"
ms.assetid: ba7864af-056a-4b7b-843d-08c45b7f7394
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::HasKey メソッド
指定したキーが現在のマップに格納されているかどうかを判定します。  
  
## 構文  
  
```  
  
bool HasKey(  
   K key  
);  
```  
  
#### パラメーター  
 `key`  
 Map 要素の検索に使用するキー。`key` の型は型名 *K* です。  
  
## 戻り値  
 キーが見つかった場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)