---
title: "UnorderedMap::HasKey メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::HasKey"
ms.assetid: 7c397cdc-82f6-470a-8a3c-f5ba2cc58ed6
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::HasKey メソッド
指定したキーが現在の UnorderedMap に格納されているかどうかを判定します。  
  
## 構文  
  
```scr  
  
bool HasKey(  
   K key  
);  
```  
  
#### パラメーター  
 `key`  
 UnorderedMap 要素の検索に使用するキー。`key` の型は型名 *K* です。  
  
## 戻り値  
 キーが見つかった場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::UnorderedMap クラス](../cppcx/platform-collections-unorderedmap-class.md)   
 [コレクション](../cppcx/collections-c-cx.md)   
 [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)