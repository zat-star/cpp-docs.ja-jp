---
title: "UnorderedMap::Lookup メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::Lookup"
ms.assetid: 6f9bb393-3791-423d-bfee-925e0531e1a5
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::Lookup メソッド
型 K の指定されたキーに関連付けられている型 V の値を取得します。  
  
## 構文  
  
```scr  
V Lookup(  
   K key  
);  
```  
  
#### パラメーター  
 `key`  
 UnorderedMap の要素の検索に使用するキー。`key` の型の型名は *K* です。  
  
## 戻り値  
 `key` とペアになる値。 戻り値の型は、型名 *V* です。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [コレクション](../cppcx/collections-c-cx.md)   
 [Platform::Collections::UnorderedMap クラス](../cppcx/platform-collections-unorderedmap-class.md)