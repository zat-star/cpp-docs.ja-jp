---
title: "UnorderedMapView::Split メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::Split"
ms.assetid: b759d254-40c9-40f1-9838-106ffb2c5626
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::Split メソッド
現在の UnorderedMapView オブジェクトを 2 つの UnorderedMapView オブジェクトに分割します。 このメソッドは操作不可です。  
  
## 構文  
  
```cpp  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * secondPartition  
);  
```  
  
#### パラメーター  
 `firstPartition`  
 元の UnorderedMapView オブジェクトの最初の部分。  
  
 `secondPartition`  
 元の UnorderedMapView オブジェクトの 2 つ目の部分。  
  
## 解説  
 このメソッドは操作可能ではありません。これは何も実行しません。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)