---
title: "Map::Lookup メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Lookup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Lookup メソッド"
ms.assetid: c56773ae-2df0-4d21-a6ab-9603529547b0
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Lookup メソッド
キーがある場合は、型 K の指定されたキーに関連付けられている型 V の値を取得します。  
  
## 構文  
  
```  
V Lookup(  
   K key  
);  
```  
  
#### パラメーター  
 `key`  
 マップの要素の検索に使用するキー。`key` の型は型名 *K* です。  
  
## 戻り値  
 `key` とペアになる値。 戻り値の型は、型名 *V* です。  
  
## 解説  
 キーが存在しない場合、[Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) がスローされます。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)   
 [コレクション \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)