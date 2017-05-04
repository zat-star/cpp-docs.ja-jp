---
title: "UnorderedMapView::HasKey メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::HasKey"
ms.assetid: 4704da18-8606-4df7-be51-d125b2e4aee0
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::HasKey メソッド
指定したキーが現在の UnorderedMap に格納されているかどうかを判定します。  
  
## 構文  
  
```cpp  
  
bool HasKey(  
   K key  
);  
```  
  
#### パラメーター  
 `key`  
 要素の検索に使用するキー。`key` の型は型名 *K* です。  
  
## 戻り値  
 キーが見つかった場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::UnorderedMap クラス](../cppcx/platform-collections-unorderedmap-class.md)   
 [コレクション](../cppcx/collections-c-cx.md)   
 [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)